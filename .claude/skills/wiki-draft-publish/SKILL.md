---
name: wiki-draft-publish
description: Put a repo draft from support-staging/articles/ into wiki.cuebly.com under drafts/ with the Wiki.js API, or update a draft page that is already there, including its images. Use when asked to put, upload, publish or refresh a draft in the wiki. Never for live pages outside drafts/.
---

# Put a draft into the wiki (drafts/ only)

David van der Berg's checklist. The repo Markdown is the source; the wiki draft is a copy for review.

## Rules that never bend

- **Nothing outside `drafts/`, ever.** Pages under `drafts/<section>/<slug>`, assets in folders under `drafts/`. No page, folder or upload anywhere else, also not as a test, unless Jarno asks for that test himself.
- **Never create asset folders outside `drafts/`.** Wiki.js 2.5 does not check the path when a folder is created (tonight's test made the root folder `zz-permission-test` by accident, Q13).
- Work as the Wiki.js user "David" (Local, group "David API"), so "Last edited by" shows David. Do not use `WIKI_API_KEY` any more: an API key is booked on Administrator.
- Never print or store the credentials or the token in the repo, the board or a chat. They are in `WIKI_DAVID_EMAIL` and `WIKI_DAVID_PASSWORD`; send them and the token only to `https://wiki.cuebly.com/graphql` and `https://wiki.cuebly.com/u`.
- Going live (outside `drafts/`) is the go-live switch in `plan/cutover.md`, with Jarno's approval. Not this skill.

## Log in

Log in once per session and keep the token in a file in the scratchpad (mode 600), never in the repo:

```
mutation($u: String!, $p: String!) {
  authentication { login(username: $u, password: $p, strategy: "local") {
    jwt responseResult { succeeded message } } }
}
```

Pass `WIKI_DAVID_EMAIL` and `WIKI_DAVID_PASSWORD` as variables from Python (`os.environ`), print only `responseResult`, and send the `jwt` as `Authorization: Bearer <jwt>` on every call below. When a call says the token expired, log in again.

## What the user can do (group "David API")

Tested 2026-10-22 with the user: `pages.single` and `pages.update` under `drafts/` work; "Last edited by" shows David after an update. The rest of the table was tested 2026-10-21 with the old API key of the same group; Jarno has since added the right to manage and move pages. Re-test a row before relying on it.

| Call | Result |
|---|---|
| `pages.list` | works, public pages only |
| `pages.single` | works (tested with the user, 2026-10-22) |
| `pages.create`, `pages.update` under `drafts/` | works |
| `pages.create` outside `drafts/` | refused (6010) |
| `pages.move` | allowed by Jarno (2026-10-22, key test: id 115 moved). Never out of `drafts/` without Jarno's approval |
| `pages.render` | refused with the key; not tested with the user |
| `assets.createFolder` | works anywhere: not path checked, see the rule above |
| upload (`/u`) into a `drafts/` folder | works; into the root folder refused |
| delete page, delete folder | not possible with the key; page delete not tested with the user (no folder delete in Wiki.js 2.5) |

Easiest is a small Python helper in the scratchpad (`urllib`, CA bundle `/root/.ccr/ca-bundle.crt`) that logs in and posts queries with variables. A Claude Code permission rule in `.claude/settings.json` also allows `curl * https://wiki.cuebly.com/graphql *` (URL right after `curl`).

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
   `curl -sS https://wiki.cuebly.com/u -H "Authorization: Bearer $(cat <token file>)" -F 'mediaUpload={"folderId":<id>}' -F "mediaUpload=@<file>;type=image/png"` returns `ok`.
3. Check with `{ assets { list(folderId: <id>, kind: ALL) { filename fileSize } } }`.
4. To replace an image, upload the new one under the same name and check that `fileSize` changed. Tested 2026-10-23: the upload replaces the file in place (same asset id, new size and `updatedAt`), no duplicate.

## 4. Create or update the page

- New: `pages { create(content, description, editor: "markdown", isPublished: true, isPrivate: false, locale: "en", path: "drafts/<path>", tags: [], title) }`.
- Existing: `pages { update(id, content, tags: []) }`. The same call with unchanged content re-saves a page under David's name. `tags` is required, or the update fails with "Cannot read properties of undefined (reading 'map')".
- Check `responseResult.succeeded`. Note the page id, add it to `plan/page-ids.md`, and replace every `/en/<final path>` link to this page in the other drafts with `/i/<id>` (`grep -rn "/en/<final path>" support-staging/articles`).

## 5. Check and log

- As a guest (no token): `https://wiki.cuebly.com/en/drafts/<path>` and one image must give HTTP 403.
- Add a row to `support-staging/CHANGELOG.md`, fill the wiki draft column in `plan/cutover.md`, commit to Business-processes `main`.
- Send Manon the URL and the page id (send_message, `@parent`).
