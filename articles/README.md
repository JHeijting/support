# Wiki article drafts

Markdown drafts for wiki.cuebly.com (Wiki.js), written by David van der Berg (wiki, cloud). Nothing here is published; Jarno approves every article first.

## Structure

The folders follow the wiki's own paths. `reseller-environment/account-management.md` becomes `https://wiki.cuebly.com/en/reseller-environment/account-management`.

## Each draft has

- A header block with the wiki path, title, description, status, sources and the date of the last fact check.
- The article text, in customer and reseller language: short sentences, task first.
- Images as `![alt text](/wiki-images/<set>/<file>.png)` with the caption in italics below. The images are Art's, in frontend-design `wiki-images/`, always built from Tess's real screenshots (team README, "Wiki images: the update loop"); alt text and captions come from Art's alt text files. When publishing, upload them to the wiki and adjust the path. An image that does not exist yet stays a placeholder `![alt text](image: <name>)`, requested from Art in `team/board/art.md`.
- A closing section **Draft notes (remove before publishing)**: what is not verified by Tess, open bugs that affect the text, and questions. Statements in the article that are not verified carry the mark `[unverified]`; remove the mark once checked, or remove the statement.

## Status values

`draft` (written, not checked), `check` (waiting for Tess or Jarno on a fact), `review` (ready for Jarno), `approved`, `published`.
