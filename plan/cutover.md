# Wiki cutover plan for the go-live

Owner: David van der Berg. Status: draft, 2026-10-21.

All new and rewritten pages stay drafts until the official go-live of the new platform. At go-live the wiki changes in one planned switch, following this plan. After go-live the wiki is kept up to date page by page, and every change goes into `support-staging/CHANGELOG.md`.

## Rules

- **Current product only.** The wiki describes how Cuebly works now: no version names (no V3, no V4), no "What changed" sections, no comparisons with before (Jarno, 2026-10-21). The configurator is called DevCon.
- **Drafts live under `drafts/` in the wiki** (not visible to guests) and as Markdown in `support-staging/articles/`. The Markdown is the source; the wiki draft is a copy for review.
- **Replace, do not recreate.** A live page that gets a rewrite keeps its id, path and history: at go-live its content is replaced with the draft (`pages.update` on the live id). Links from outside keep working.
- **New pages move to their final path** with `pages.move` of the draft, never `pages.create` at the final path: moving keeps the page id, and links between pages use the id (`/i/<id>`, see `plan/page-ids.md`). Recreating a page would break those links.
- **Images move with their page.** Each page's images are uploaded to the page's final asset folder (see "Images" below), and the image links in the page are changed to that folder in the same step. A page never goes live with links to `drafts/`.
- **Nothing is published without Jarno's approval.** The go-live switch is one approval for the whole list below, after a final review of each draft.
- **"Last edited by" shows David van der Berg** (Jarno, 2026-10-22), also after go-live, so pages from this process can be told from pages written by hand. Wiki.js 2.5 books every API key request on user 1 (Administrator), so the drafts made so far show "Administrator". Jarno creates a Local user "David van der Berg" in group "David API"; a later session logs in with `authentication.login` and uses that token. At go-live, either David gets write rights on the live paths and does the switch himself, or he re-saves each switched page right after, so every live page shows his name. Done 2026-10-22: the Local user exists (display name "David"), the drafts 115 to 117 were re-saved and show "Last edited by David".
- **Rights:** David's key can write only under `drafts/`. The switch needs a key with write rights on the live paths for that night, or Jarno runs it. To be decided by Jarno.

## Pages that get a rewrite (content replaced, same path)

| Live path | Draft (`support-staging/articles/`) | Wiki draft | Images to move |
|---|---|---|---|
| `home` | `home.md` | | |
| `about-cuebly/supported-languages` | `about-cuebly/supported-languages.md` | | |
| `cuebly-app` | `cuebly-app.md` | | per draft |
| `cuebly-app/faq` | `cuebly-app/faq.md` | | per draft |
| `cuebly-app/geofencing` | `cuebly-app/geofencing.md` | | per draft |
| `cuebly-app/onboarding` | `cuebly-app/onboarding.md` | | per draft |
| `cuebly-app/settings` | `cuebly-app/settings.md` | | per draft |
| `customer-environment` | `customer-environment.md` | | per draft |
| `customer-environment/alerts` | `customer-environment/alerts.md` | | per draft |
| `customer-environment/alerts/script` | `customer-environment/alerts/script.md` | | per draft |
| `customer-environment/dashboards` | `customer-environment/dashboards.md` | | per draft |
| `customer-environment/scenarios` | `customer-environment/scenarios.md` | | per draft |
| `customer-environment/scenarios/actions` | `customer-environment/scenarios/actions.md` | | per draft |
| `customer-environment/scenarios/triggers` | `customer-environment/scenarios/triggers.md` | | per draft |
| `customer-environment/teams` | `customer-environment/teams.md` | | per draft |
| `customer-environment/users` | `customer-environment/users.md` | | per draft |
| `reseller-environment/account-management` | `reseller-environment/account-management.md` | | per draft |
| `reseller-environment/device-management` | correction only: `reseller-environment/device-management-arc-fix.md` replaces the ARC passage; a full rewrite is still to be written | | |

## New pages (move to the final path)

| Final path | Draft | Wiki draft | Images to move |
|---|---|---|---|
| `reseller-environment/account-management/presentation-mode` | `reseller-environment/account-management/presentation-mode.md` | `drafts/reseller-environment/account-management/presentation-mode` (id 115) | asset folder `drafts/presentation-mode`, images 01 to 05 |
| `customer-environment/devices/devcon` | `customer-environment/devices/devcon.md` | | per draft |
| `reseller-environment/device-management/add-app-user` | `reseller-environment/device-management/add-app-user.md` | | per draft |
| `reseller-environment/device-management/import-devices` | `reseller-environment/device-management/import-devices.md` | | per draft |
| `cuebly-app/availability-presence` | `cuebly-app/availability-presence.md` | | per draft |
| `cuebly-app/send-help` | `cuebly-app/send-help.md` | | per draft |
| `cuebly-app/timer-alarm` | `cuebly-app/timer-alarm.md` | | per draft |

The wiki inventory (`plan/wiki-inventory.md`) lists more new pages that are not written yet (custom views, quick button, device types, messages in the app, alarm receiving centre management). They join this table when their draft exists.

**Dropped from the plan:** N11 "What is new in V4". It conflicts with the rule "current product only".

## May go live before the go-live (Jarno, T18)

True today and free of version names. Jarno decides when; it is not part of the switch.

| Final path | Draft | Wiki draft | How |
|---|---|---|---|
| `supported-devices/location-in-alarms` | `supported-devices/location-in-alarms.md` | `drafts/supported-devices/location-in-alarms` (id 116) | new page |
| `supported-devices/personal-trackers/twig` | `supported-devices/personal-trackers/twig.section-behaviour.md` | `drafts/supported-devices/personal-trackers/twig-behaviour` (id 117) | insert the section before "MPTP protocol explained" |
| `supported-devices/personal-trackers/twig-one`, `-neo`, `-embody`, `-protector-pro`, `-sos-card` | `supported-devices/personal-trackers/<model>.section-behaviour.md` | in id 117 (model line) | insert the section after "Configuration options" |

## Proposal: one brand page per brand (Jarno, J9, 2026-10-22)

**Status: proposal, waiting for Jarno.** Nothing is moved yet.

Jarno: "Shouldn't this go under supported devices and then Twig? So that every brand gets a brand page with the relevant info about it?"

**Today:** device pages sit in two category folders, and brands are mixed. Twig has a brand page (`personal-trackers/twig`, protocol and firmware) with its models next to it, not below it. Queclink and Eview have a near-empty brand page with the model below it. Teltonika has models in both folders and no brand page. Emerit and Elexol have no brand page.

**Proposed structure:** `supported-devices/<brand>/<model>`.

- **Brand page** `supported-devices/<brand>`: what all models share. Fixed sections, each only if there is something to say: **Models** (list with type: personal alarm, gateway, app), **How <brand> devices behave** (the device behaviour pattern, brand level), **Configuration** (DevCon settings shared by all models), **Firmware**, **Connect to the platform** (when the settings are the same for every model).
- **Model page** `supported-devices/<brand>/<model>`: what is specific to the model (features, configuration table, connection settings if they differ, **How this device behaves** only for what differs). The model slug drops the brand name (`twig/one`, not `twig/twig-one`); the title keeps it ("Twig One").
- **Type overview pages stay** at their current paths (`supported-devices/personal-trackers`, `supported-devices/gateways`): a short list of models of that type, linking to the model pages. Customers who look for "a personal alarm" still find a list.
- **New page** `supported-devices`: overview of all brands and the two type lists.
- **Device-neutral pages** stay directly under `supported-devices` (for example `location-in-alarms`).

**Moves** (all keep their id, so `/i/<id>` links keep working):

| Id | From | To |
|---|---|---|
| 71 | `supported-devices/personal-trackers/twig` | `supported-devices/twig` |
| 101 | `.../personal-trackers/twig-easy` | `supported-devices/twig/easy` |
| 5 | `.../personal-trackers/twig-embody` | `supported-devices/twig/embody` |
| 108 | `.../personal-trackers/twig-eon` | `supported-devices/twig/eon` |
| 6 | `.../personal-trackers/twig-neo` | `supported-devices/twig/neo` |
| 8 | `.../personal-trackers/twig-one` | `supported-devices/twig/one` |
| 7 | `.../personal-trackers/twig-one-ex` | `supported-devices/twig/one-ex` |
| 12 | `.../personal-trackers/twig-protector` | `supported-devices/twig/protector` |
| 9 | `.../personal-trackers/twig-protector-ex` | `supported-devices/twig/protector-ex` |
| 11 | `.../personal-trackers/twig-protector-pro` | `supported-devices/twig/protector-pro` |
| 10 | `.../personal-trackers/twig-protector-pro-ex` | `supported-devices/twig/protector-pro-ex` |
| 13 | `.../personal-trackers/twig-sos-card` | `supported-devices/twig/sos-card` |
| 14 | `.../personal-trackers/teltonika-tmt250` | `supported-devices/teltonika/tmt250` |
| 15 | `.../personal-trackers/teltonika-gh5200` | `supported-devices/teltonika/gh5200` |
| 85 | `supported-devices/gateways/teltonika-fmc640` | `supported-devices/teltonika/fmc640` |
| 86 | `supported-devices/gateways/teltonika-fmc650` | `supported-devices/teltonika/fmc650` |
| 16 | `.../personal-trackers/emerit-ewg100` | `supported-devices/emerit/ewg100` |
| 111 | `.../personal-trackers/emerit-ewg200` | `supported-devices/emerit/ewg200` |
| 89 | `.../personal-trackers/emerit-connect` | `supported-devices/emerit/connect-app` |
| 77 | `.../personal-trackers/queclink` | `supported-devices/queclink` |
| 78 | `.../personal-trackers/queclink/GL320MG` | `supported-devices/queclink/gl320mg` |
| 81 | `.../personal-trackers/eview` | `supported-devices/eview` |
| 82 | `.../personal-trackers/eview/ev-04` | `supported-devices/eview/ev-04` |
| 87 | `supported-devices/gateways/elexol-ip2espa-v1` | `supported-devices/elexol/ip2espa-v1` |
| 88 | `supported-devices/gateways/elexol-ip2espa-v2` | `supported-devices/elexol/ip2espa-v2` |

**New brand pages** (short at first: models list and what is verified as shared): `supported-devices/teltonika`, `supported-devices/emerit`, `supported-devices/elexol`, plus the overview `supported-devices`. Each starts under `drafts/` like any new page. Later brands from the inventory (N15 to N17: more Eview models, Twig Neo Ex and remote button, Emerit e-RG360, Ajax, Moxa) go straight into this structure.

**What changes elsewhere:**

- The Queclink and Eview merges (section above) are dropped: their parent pages become brand pages instead.
- Twig behaviour: the brand section (draft id 117) goes on the brand page `supported-devices/twig`; the model lines on the model pages. Draft 117 can move to `drafts/supported-devices/twig/behaviour`.
- The two type overview pages (ids 4 and 84) get a rewrite: lists by type, linking to the model pages.
- Internal links: links that use `/en/<path>` on live pages break on a move. Before the moves, replace them with `/i/<id>` on every page that is touched (pages.list plus a search for `/en/supported-devices/`).

**Risk to check before the moves:** Wiki.js 2.5 does not keep a redirect from the old path after a move [unverified, test on a draft]. Links from outside the wiki (the platform, the app, manuals, partner documents, search engines) to `/en/supported-devices/personal-trackers/...` would then give a 404. Before moving: ask Jarno and the developers whether the platform or app link to device pages by path; if so, change those links to `/i/<id>` first.

**When:** the structure can change before the V4 go-live, because device pages describe today's devices. Proposed order: (1) Jarno approves the structure, (2) test on a draft whether the old path redirects, (3) links to `/i/<id>`, (4) create the brand pages under `drafts/` for review, (5) move the live pages in one go with Jarno's approval, log every move in `CHANGELOG.md`.

## Live pages to remove at go-live (Jarno to confirm each)

| Live path | Why |
|---|---|
| `reseller-environment/reports` | "Coming soon" only |
| `about-cuebly` | title only, unless Jarno wants a company page |
| `cuebly-app/whitelabel` | replaced by one app with the account's branding (Jarno to confirm); a short replacement page may follow |
| `customer-environment/quick-texts` | no menu in the new customer environment |
| `customer-environment/alarm-protocols` | no page in the new customer environment; devices have an Alarm protocol field |
| `customer-environment/assistance-requests` | an assistance request is now an alarm type, sent with a scenario action |
| `cuebly-app/assistance-requests` | not in the new app |
| `cuebly-app/e-b10` | pairing not in the new app |
| `reseller-environment/account-management/modules` | modules are not part of an account (proposal 006 is a direction, not built) |
| `customer-environment/dashboards/tiles` | custom dashboards are not available; rewrite instead if they come |

Each of these is open in the inventory's questions until Jarno decides. Before removal, check which pages link to it and fix those links in the same switch.

**Merges** (from the inventory): `supported-devices/personal-trackers/eview` into `eview/ev-04` (or a short list page), `supported-devices/personal-trackers/queclink` into `queclink/GL320MG`. Dropped if the brand page proposal (above) is approved.

## Live pages that stay

All other public pages stay as they are, or get small updates after go-live (device pages: check their configuration tables against DevCon; beacons, translations, site, SIM card and financial pages: check against the new platform). Those updates go into the changelog one by one.

## Images

- The repo source for images is frontend-design `wiki-images/<set>/`, built by Art from Tess's screenshots. Drafts link to `/wiki-images/<set>/<file>`.
- In the wiki, drafts use asset folders under `drafts/` (for example `drafts/presentation-mode`).
- Before an image goes into a wiki draft or live page, check frontend-design `wiki-images/wiki-drafts-image-map.md`: images with status "old test names" wait for Tess's retake and Art's re-render. Open now: presentation mode 03 to 05 (already in `drafts/presentation-mode`, to be replaced under the same names).
- **At go-live each page's images move with it:** upload them to the page's final asset folder, named after the page's section and slug (for example `reseller-environment/account-management/presentation-mode`), change the image links in the page, and check the page as a guest. Old V3 screenshots that a rewritten page no longer uses can then be removed.
- Art's concept diagrams (`wiki-images/diagrams/`) are used in several drafts. The alt text of the DevCon sync diagram said "DevCon V4" and "legacy DevCon" (now removed from the draft). If the image itself shows those words, Art must re-render it without version names before go-live.

## The switch, step by step

1. Final review: every draft in the tables above has status `review`, no `[unverified]` marks, and Jarno's approval.
2. Upload the images of every page to its final asset folder.
3. Replace the content of the rewritten pages, with the image links pointing to the final folders. Remove the Draft notes from the page body (they stay in the repo).
4. Move or create the new pages at their final paths.
5. Remove the pages Jarno confirmed, after fixing links to them.
6. Check as a guest: every page in this plan opens, every image loads, no link points to `drafts/`.
7. Delete the wiki drafts, the `drafts/` asset folders and the test page `drafts/zz-permission-test` (id 114).
8. Log everything in `support-staging/CHANGELOG.md` as one go-live entry.

Signed: David van der Berg
