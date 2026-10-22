# Wiki link fixes for the brand page moves and the go-live (J16 step 3)

Prepared by David van der Berg on 2026-10-22, for Jarno to approve as one batch. Nothing has been changed on live pages.

**How it was checked:** all 73 live pages, read as public rendered HTML (my wiki user cannot read the source of live pages). Links in the page content only: 137 id links (`/i/<id>`), 13 path links, 26 external links.

## 1. Brand page moves: no wiki link changes needed

Every link between live pages that points to a device page is already an id link (`/i/<id>`), and those keep working after a move. No path link points to a page that moves.

**Checked by Jarno in the editor (J17.3): the links are id links.** The original check: the rendered pages show `/i/<id>`. Please open the source of one page in the editor (for example **Personal alarms**, `supported-devices/personal-trackers`) and confirm that its links are written as `/i/<id>`. If the source has paths and Wiki.js only shows them as ids, the moves need the link fixes after all, and I list them from the editor.

Downloads (`/downloadable-files/...`) are asset files, not pages. They do not move with the pages.

## 2. Broken links today (fix now, with approval)

| Page | Id | Link now | Fix |
|---|---|---|---|
| `reseller-environment/device-management` | 35 | `/personal-trackers` (404) | `/i/4` (Personal alarms) |
| `reseller-environment/account-management/modules` | 95 | `/i/i62` (broken) | none: the page is removed at go-live |

## 3. Links to pages that are removed or parked at go-live

| From (id, page) | To (id, page) | Covered by |
|---|---|---|
| 18 `customer-environment` | 21 alarm protocols, 23 assistance requests, 27 quick texts | rewrite draft (no such links) |
| 19 `customer-environment/dashboards` | 91 dashboard tiles | rewrite draft |
| 22 `customer-environment/devices` | 21 alarm protocols, 27 quick texts | **no draft yet: remove the two links in the switch** |
| 28 `customer-environment/scenarios` | 23 assistance requests | rewrite draft |
| 29 `cuebly-app` | 61 whitelabel, 92 app assistance requests, 96 e-B10 | rewrite draft |
| 34 `reseller-environment/account-management` | 95 modules | rewrite draft |
| 79 `customer-environment/scenarios/triggers` | 23 assistance requests | rewrite draft |
| 80 `customer-environment/scenarios/actions` | 23 assistance requests | rewrite draft |
| 94 `customer-environment/alerts/script` | 21 alarm protocols | rewrite draft |
| 23, 27, 92, 95 (pages that are parked or removed themselves) | each other | nothing to do |

Checked: none of the drafts links to a removed or parked page. If `customer-environment/assistance-requests` (id 23) is rewritten instead of parked, the links to it stay.

## 4. Website links

See `plan/external-links.md` (Manon). Fixed in the same switch, with Jarno's approval.

## To approve

- [x] Section 2: fix the broken link on device management (id 35) now. Approved (J17.1). Not done yet: David's wiki user cannot read or edit live pages (write only under `drafts/`). Jarno fixes it in the editor, or gives the user rights on this page.
- [x] Section 3: remove the two links on `customer-environment/devices` (id 22) in the go-live switch. Approved (J17.2); in `plan/cutover.md`.
