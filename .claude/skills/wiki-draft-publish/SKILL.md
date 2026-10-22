---
name: wiki-draft-publish
description: Put a repo draft from support-staging/articles/ into wiki.cuebly.com under drafts/ with the Wiki.js API, or update a draft page that is already there, including its images. Use when asked to put, upload, publish or refresh a draft in the wiki. Never for live pages outside drafts/.
---

# Put a draft into the wiki (drafts/ only)

David van der Berg's checklist. The repo Markdown is the source; the wiki draft is a copy for review.

## Rules that never bend

- **Nothing outside `drafts/`, ever.** Pages under `drafts/<section>/<slug>`, assets in folders under `drafts/`. No page, folder or upload anywhere else, also not as a test, unless Jarno asks for that test himself.
- **Never create asset folders outside `drafts/`.** Wiki.js 2.5 does not check the path when a folder is created (tonight's test made the root folder `zz-permission-test` by accident, Q13).
- Never print or store the key. It is in `WIKI_API_KEY`; send it only to `https://wiki.cuebly.com/graphql` and `https://wiki.cuebly.com/u`.
- Going live (outside `drafts/`) is the go-live switch in `plan/cutover.md`, with Jarno's approval. Not this skill.

## What the key can do (group "David API", tested 2026-10-21)

| Call | Result |
|---|---|
| `pages.list` | works, public pages only |
| `pages.single`, `pages.singleByPath` | refused: they need `manage:pages` or `delete:pages`. Read public pages as rendered HTML (`https://wiki.cuebly.com/en/<path>`) without the key |
| `pages.create`, `pages.update` under `drafts/` | works |
| `pages.create` outside `drafts/` | refused (6010) |
| `pages.render`, `pages.move` | refused everywhere: they need `manage:pages` globally |
| `assets.createFolder` | works anywhere: not path checked, see the rule above |
| upload (`/u`) into a `drafts/` folder | works; into the root folder refused |
| delete page, delete folder | not possible with this key (and no folder delete in Wiki.js 2.5) |

A Claude Code permission rule in `.claude/settings.json` allows `curl * https://wiki.cuebly.com/graphql *`. Put the URL right after `curl` so the rule matches.

## 1. Check the draft

- Status `review` or Jarno asked for it; no em-dashes; current product only (no V3, V4, "What changed").
- For every image: look it up in frontend-design `wiki-images/wiki-drafts-image-map.md`. Status "old test names" means: leave that image out and say so.

## 2. Build the page body

From `support-staging/articles/<path>.md`:

- front matter `title` and `description` become the page's title and description;
- drop the front matter, the H1 (Wiki.js shows the title) and everything from `---` + `## Draft notes` on;
- change image links `/wiki-images/<set>/<file>` to `/drafts/<page-slug>/<file>`.
- check the links: every link is `/i/<id>` (link rule in `articles/README.md`). A remaining `/en/<path>` link must point to a new page listed in `plan/page-ids.md` under "New pages without an id yet".

Build the request with Python (`json.dump` with GraphQL variables), never by hand-escaping Markdown.

## 3. Images

1. Find the folder: `{ assets { folders(parentFolderId: 0) { id slug } } }`, then the children of `drafts` (id 24). Create `drafts/<page-slug>` only if missing: `assets { createFolder(parentFolderId: 24, slug: "<page-slug>") }`.
2. Upload each image under its own file name:
   `curl -sS https://wiki.cuebly.com/u -H "Authorization: Bearer $WIKI_API_KEY" -F 'mediaUpload={"folderId":<id>}' -F "mediaUpload=@<file>;type=image/png"` returns `ok`.
3. Check with `{ assets { list(folderId: <id>, kind: ALL) { filename fileSize } } }`.
4. To replace an image, upload the new one under the same name and check that `fileSize` changed (not tested yet; if the size stays the same, ask Manon).

## 4. Create or update the page

- New: `pages { create(content, description, editor: "markdown", isPublished: true, isPrivate: false, locale: "en", path: "drafts/<path>", tags: [], title) }`.
- Existing: `pages { update(id, content, tags: []) }`. `tags` is required, or the update fails with "Cannot read properties of undefined (reading 'map')".
- Check `responseResult.succeeded`. Note the page id, add it to `plan/page-ids.md`, and replace every `/en/<final path>` link to this page in the other drafts with `/i/<id>` (`grep -rn "/en/<final path>" support-staging/articles`).

## 5. Check and log

- As a guest (no key): `https://wiki.cuebly.com/en/drafts/<path>` and one image must give HTTP 403.
- Add a row to `support-staging/CHANGELOG.md`, fill the wiki draft column in `plan/cutover.md`, commit to Business-processes `main`.
- Send Manon the URL and the page id (send_message, `@parent`).
