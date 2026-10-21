---
name: wiki-update
description: Turn a tested product change into a wiki update - from a GitLab test comment with release notes input (Tess's template) or a change in frontend-design knowledge/ to an updated draft, image requests, a changelog entry and a wiki draft under drafts/. Use when Tess, Manon or Jarno report a change that the wiki must follow.
---

# From a tested change to a wiki update

David van der Berg's checklist for the wiki part (cloud, public knowledge only).

## Rules that never bend

- **Current product only.** No V3, no V4, no "What changed" sections, no comparisons with before. The configurator is called DevCon.
- **Only verified facts.** Tested by Tess, or in the product notes, or decided by Jarno. Anything else gets `[unverified]` in the text and a line in the Draft notes.
- **No invented intent** ("this is on purpose") and **no bugs as behaviour**: a bug is not documented and gets no workaround. It goes in the Draft notes with its ticket id.
- **Never outside `drafts/`** in the wiki. Live pages change only in the go-live switch (`plan/cutover.md`) or, after go-live, with Jarno's approval per change.
- No customer names, ticket contents or mail. Images only from Tess's real screenshots (Art's sets), never drawn, never with old test names.
- English, no em-dashes. Writing rules: `support-staging/articles/README.md`.

## 1. Read the input

- **GitLab test comment:** the result (passed only; a failed or blocked test changes nothing in the wiki) and the release notes input from Tess's template (frontend-design `qa/README.md`, `qa/templates/release-note.md`).
- **knowledge/ change:** frontend-design `knowledge/modules/<module>.md`, its "Wiki notes", `glossary.md`.
- Write down in one line what changed for the user, and which ticket or release it comes from.

## 2. Find the pages

- Search `support-staging/plan/wiki-inventory.md` for the module, the screen and the terms (also old names).
- Search the drafts too: `grep -rl "<term>" support-staging/articles/`.
- A change can hit a draft, a live page without a draft yet, or call for a new page. A new page goes into the inventory's "New pages" table first.

## 3. Update the draft

- Change only what the change touches. Task-first, short sentences.
- Front matter: `sources` (add the ticket or knowledge file), `last fact check` (today).
- Draft notes: what is still open, bugs with their ids, Jarno's decisions.
- If a live page has no draft yet, start one from the live page's rendered text (public HTML, no key) in the draft format of `articles/README.md`.

## 4. Images

- Check frontend-design `wiki-images/wiki-drafts-image-map.md` for the page.
- When a screen changed: ask Tess for a retake and Art for a re-render under the same file name, in their board files (`team/board/tess.md`, `team/board/art.md`). Name the image file, what changed and the page.
- Until then: leave the image out, or keep the old one only if it still shows the right screen.

## 5. Log

- `support-staging/CHANGELOG.md`: date, wiki path, change, why, ticket or release, your name.
- `plan/cutover.md`: add a new page or a page to remove. After go-live, the changelog alone.
- `team/board/david.md`: one log entry. Commit to Business-processes `main` (pull first). Republish the board only if someone else must act.

## 6. Into the wiki under drafts/

Follow the `wiki-draft-publish` skill. Then send Manon (send_message, `@parent`): the change, the pages, the draft URL, the image requests and open questions for Jarno.
