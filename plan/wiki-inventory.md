# Wiki inventory and V4 update plan

**Owner:** David van der Berg (wiki, cloud)
**Task:** T2, updated in T10 with Tess's wiki report
**Date:** 2026-10-21
**Status:** draft for Jarno's review
**Location:** Business-processes `support-staging/plan/` (Manon copies it to the `support` repo)

## How this was made

- Page list from the wiki's GraphQL API (`pages.list`): **78 pages, all English, all published.**
- Page text from the public rendered pages (`https://wiki.cuebly.com/en/<path>`). The GraphQL `pages.single` query is not open without a key (error "You are not authorized to view this page"), so the API alone is not enough to read content.
- V4 facts from Tess's knowledge in frontend-design `knowledge/` (module files, glossary, fact sheet of 2026-10-21, `2026-10-21-wiki-gaps.md`, `v4-gaps.md`) and the screenshot index in `current/`.
- **Not verified by Tess** is marked as `(unverified)`. That means the wiki page may still be right for V4, but nobody has checked it on V4 dev yet. Those pages wait for T4 (Tess's wiki report) before anything is rewritten.

## Update after Tess's wiki report (T10)

Tess's report (frontend-design `knowledge/wiki-report.md`, T4) agrees with this inventory on almost every page. What changed here:

- **Presentation mode is documented** (frontend-design `knowledge/modules/presentation-mode.md`). Draft written: `support-staging/articles/reseller-environment/presentation-mode.md` (N1).
- **The ARC sentence on `reseller-environment/device-management` is wrong for V4:** V4 cannot hide scenarios from the customer. Correction drafted: `support-staging/articles/reseller-environment/device-management-arc-fix.md`.
- **No menu in the V4 customer environment** for Quick texts, Alarm protocols and Assistance requests. Assistance requests are sent with the scenario action "Send assistance request"; devices have an "Alarm protocol" field. Whether pages come back is a question for Jarno.
- **Custom dashboards:** not in V4 yet (Jarno). `dashboards` should say so; presentation pages are not the same as presentation mode.
- **Scenario triggers and actions:** the lists are "as seen on V4 dev" for one test account. Publish them with that label until Jarno confirms.
- **Beacons** are added by the account manager in V4 (Beacons menu), not only by a Cuebly integrator: `customer-environment/beacons` and `reseller-environment/beacon-management` move from Keep to Update.
- **Translations:** V4 manages translations in the platform's Translations page and the locale service; the Google Translate remark is outdated: `reseller-environment/translations` moves from Keep to Update.
- **Device types without a page in V4:** Eview EV-06, EV-07B and EV-12, Twig Neo Ex, Twig remote button, Emerit e-RG360, Ajax hub and wall alarm, Moxa IO, generic device. Added as new pages N15 to N17 (grouped).
- **New app topics:** SOS shortcuts and the Samsung XCover side button, messages in the app (proposal 009). Added as N18; N12 widened.
- **Account management in V4** also has adoption (moving an account to another account manager) and ARC pills in the lists. A page for alarm receiving centre management is proposed (N19).
- **Answers to my questions** are worked into the drafts (DevCon V4 switches, custom view sync, microphone reason, location wording, delete of archived accounts).

## Draft status (T14)

`review`: publish-ready, every fact verified by Tess or marked as a question for Jarno; its Draft notes hold only what Jarno must decide. `check`: written, waiting for the facts in its Draft notes. "Open marks" counts the `[unverified]`, `[see draft notes]` and `[Jarno: ...]` marks in the article text.

| Wiki path | Title | Kind | Status | Open marks | Draft |
|---|---|---|---|---|---|
| `customer-environment/devices/devcon` | Change device settings (DevCon) | new | review | 1 | `articles/customer-environment/devices/devcon.md` |
| `reseller-environment/device-management/add-app-user` | Add an app user | new | review | 1 | `articles/reseller-environment/device-management/add-app-user.md` |
| `reseller-environment/presentation-mode` | Presentation mode | new | review | 0 | `articles/reseller-environment/presentation-mode.md` |
| `about-cuebly/supported-languages` | Supported languages | rewrite | check | 0 | `articles/about-cuebly/supported-languages.md` |
| `cuebly-app` | Cuebly app | rewrite | check | 3 | `articles/cuebly-app.md` |
| `cuebly-app/availability-presence` | Availability, presence and connection | new | check | 0 | `articles/cuebly-app/availability-presence.md` |
| `cuebly-app/faq` | FAQ - mobile app | rewrite | check | 2 | `articles/cuebly-app/faq.md` |
| `cuebly-app/geofencing` | App geofencing | rewrite | check | 1 | `articles/cuebly-app/geofencing.md` |
| `cuebly-app/onboarding` | Onboarding | rewrite | check | 0 | `articles/cuebly-app/onboarding.md` |
| `cuebly-app/send-help` | Send an alarm with the app | new | check | 1 | `articles/cuebly-app/send-help.md` |
| `cuebly-app/settings` | App settings | rewrite | check | 2 | `articles/cuebly-app/settings.md` |
| `cuebly-app/timer-alarm` | Timer alarm | new | check | 1 | `articles/cuebly-app/timer-alarm.md` |
| `customer-environment` | Customer environment | rewrite | check | 0 | `articles/customer-environment.md` |
| `customer-environment/alerts` | Alerts | rewrite | check | 2 | `articles/customer-environment/alerts.md` |
| `customer-environment/alerts/script` | Close an alarm with the closing script | rewrite | check | 1 | `articles/customer-environment/alerts/script.md` |
| `customer-environment/dashboards` | Dashboards | rewrite | check | 2 | `articles/customer-environment/dashboards.md` |
| `customer-environment/scenarios` | Scenarios | rewrite | check | 2 | `articles/customer-environment/scenarios.md` |
| `customer-environment/scenarios/actions` | Scenario actions | rewrite | check | 4 | `articles/customer-environment/scenarios/actions.md` |
| `customer-environment/scenarios/triggers` | Scenario triggers | rewrite | check | 6 | `articles/customer-environment/scenarios/triggers.md` |
| `customer-environment/teams` | Teams | rewrite | check | 2 | `articles/customer-environment/teams.md` |
| `customer-environment/users` | Users and permissions | rewrite | check | 2 | `articles/customer-environment/users.md` |
| `home` | Cuebly Wiki home | rewrite | check | 0 | `articles/home.md` |
| `reseller-environment/account-management` | Account management | rewrite | check | 1 | `articles/reseller-environment/account-management.md` |
| `reseller-environment/device-management` | Device management (correction: ARC scenario) | correction | check | 1 | `articles/reseller-environment/device-management-arc-fix.md` |
| `reseller-environment/device-management/import-devices` | Import devices from a file | new | check | 0 | `articles/reseller-environment/device-management/import-devices.md` |

**Not written, waiting for facts:** N6 custom views and N14 quick button (custom views hidden behind a feature switch, B14, B20), N10 Groups in the app (covered by the `cuebly-app` rewrite for now), N11 what is new in V4 (after the rewrites), N15 to N17 device types (no device facts in Tess's knowledge yet: features, configuration, connection settings), N18 messages in the app (proposal 009), N19 alarm centre management (steps needed from Tess), and the rewrites of `customer-environment/devices`, `geofences`, `contacts`, `beacons`, `reseller-environment/device-management`, `user-management`, `beacon-management`, `translations` and the device pages (each needs a Tess check first, see the tables above).

## Two things for Jarno first

1. **Internal pages are public.** The five `operations/*` pages (financial, CRM, platform, telecom, other) are internal work instructions in Dutch, with internal mail addresses, system names and step-by-step admin procedures. They can be read by anyone without logging in. Advice: restrict them to a staff group in Wiki.js now, or move them to an internal place. I did not use their content for anything else.
2. **Example credentials on the Scenarios page.** The webhook example on `customer-environment/scenarios` shows a `clientId` and `secretId` that look like real values, not placeholders. Please confirm they are dummies, or have them replaced with `[CLIENT ID]` and `[SECRET ID]` as in the second example on the same page.

## Summary

| Action | Pages | Meaning |
|---|---|---|
| Keep | 37 | Correct as far as we know, no V4 impact, or not product UI (many marked "check") |
| Update text | 31 | Content is outdated or incomplete for V4 |
| Merge | 2 | Fold into another page |
| Remove or replace | 3 | Page is empty or no longer fits V4 |
| Restrict | 5 | Internal content, not for customers |
| **Total** | **78** | |
| Redo screenshots | 21 (of the pages above) | Images show V3 or the legacy app |
| New pages | 19 | V4 features and device types without a page |

Counts per page are in the tables below. A page can be both "update text" and "redo screenshots". The device pages are counted as "keep, check" until Tess or Jarno confirms their configuration tables for DevCon V4.

## Legend

- **Keep**: no change needed now.
- **Update**: rewrite parts of the text for V4.
- **Shots**: replace the screenshots or GIFs (all wiki images are V3 or the legacy app).
- **Merge**: fold into the named page.
- **Remove**: take offline or replace with a new page.
- **Restrict**: hide from the public.
- **Wait T1 / T4**: depends on Tess's presentation mode test (T1) or wiki report (T4).

## Home and About

| Page | Title | Updated | Covers | V4 change | Action |
|---|---|---|---|---|---|
| `home` | Cuebly Wiki home | 2024-04-26 | Short welcome text | Add a short "Cuebly V4" entry point: what is new, where the app pages are | Update |
| `about-cuebly` | About Cuebly | 2021-12-28 | Title only, no text | Empty page | Remove, or write a short company page (Jarno) |
| `about-cuebly/continuity-promises` | Cuebly's Continuity Promises | 2025-07-01 | SLA, status page, redundancy, escrow | Not product UI | Keep (Jarno to confirm the 99.9% and six instances still hold) |
| `about-cuebly/data-processing` | Data processing | 2025-07-01 | Retention table, change tracking list | Lists V3 entities (app seats, presentation page, modules). Check against V4 back end | Keep, check (unverified) |
| `about-cuebly/supported-languages` | Supported languages | 2025-01-23 | Language list (8) | V4 platform and app have 10 languages: add Italian and Swedish. Use own-language names: "Türkçe", "Čeština", "Svenska". Mention that the app language is chosen in the app's Settings, apart from the phone language | Update |
| `downloads` | Downloads | 2022-07-27 | Teltonika and Twig configurator and firmware | Not checked by Tess | Keep, check versions (unverified) |

## Customer environment

| Page | Title | Updated | Covers | V4 change | Action |
|---|---|---|---|---|---|
| `customer-environment` | Customer environment | 2022-08-10 | Feature list, user roles intro | Feature list includes Reports, Quick texts, custom dashboards; V4 uses per-user permissions instead of roles (see Users). Add the V4 menu and "Back to admin" | Update |
| `customer-environment/faq` | FAQ - Web | 2025-07-01 | Chrome idle detection and alarm sound | Browser behaviour, still valid | Keep |
| `customer-environment/alarm-protocols` | Alarm protocols | 2025-07-01 | Protocol fields, guardians | The protocols page is only mounted for accounts that are not V4-only (code, Tess). Mentions "disable the presentation mode" to edit instructions | Update, Wait T1 and T4 |
| `customer-environment/alerts` | Alerts | 2024-12-19 | Open and closed alerts, quick close, bulk close, auto-close, share, sound, presentation page | V4: list with type, device and time; "Alarm auto-close after" in the header (default 30 days); bulk close is an unlabelled check icon without notes; map on the right. The "show on alarm page" scenario action is not in V4. Share and presentation page not verified | Update, Shots |
| `customer-environment/alerts/script` | Alarm script | 2025-07-01 | V3 closing script, steps and activity diagram | V4 closing script: alarm type and explanation, panic word and cancellation code, Call device, then the outcome (offer help, false or test alarm, verified alarm, situation not clear, no answer), notes, Close alarm. Time to close is recorded. Full follow-up protocol is not in V4 yet (Jarno) | Update, Shots |
| `customer-environment/assistance-requests` | Assistance requests | 2025-07-01 | Send manually, response dashboard, statuses | Since V4 an assistance request is an alarm type (glossary). The page is only mounted for accounts that are not V4-only (code). Dashboard tiles New assistance request and Active assistance requests exist | Update, Wait T4 |
| `customer-environment/beacons` | Beacons | 2025-02-27 | Edit, show on map | V4: beacons are added by the account manager (Beacons menu), not only by a Cuebly integrator; map placement issue reported (v4-platform#478) (wiki report) | Update, Shots |
| `customer-environment/contacts` | Contacts | 2025-07-01 | Contact fields, availability, create user from contact | V4 screenshot exists (`platform-v4/contacts/01-contact.png`), fields not verified | Keep, Shots, check (unverified) |
| `customer-environment/dashboards` | Dashboards | 2025-07-01 | Custom dashboards, tiles, presentation pages | Conflicting sources: Jarno says custom dashboards are not in V4 yet; Tess saw a dashboard picker with `+` and a tile library on dev. Presentation pages not verified | Update, Shots, Wait T1 |
| `customer-environment/dashboards/tiles` | Dashboard tiles | 2026-03-10 | Tile descriptions | V4 library: Attendance board, Free text, Live map, Team overview, Device information, Start scenario, Enable or disable scenarios, New assistance request, Active assistance requests, Open alarms, Days without alarms, Credits, Incomplete devices, Update needed, Trial period, iframe. New: iframe, size switch Small, Medium, Large, the orange "needs to be configured" badge. Renamed: Attendance overview to Attendance board, Pending to Active assistance requests. Open alerts tile still on the default dashboard (difference unexplained, B32) | Update |
| `customer-environment/devices` | Devices | 2025-07-01 | Device status, edit fields, messages, configurator, diagnostics, connect, device URLs | V4: device cards with map; gear icon "Change device configuration" opens DevCon V4 (V4 and Emerit devices) or the legacy DevCon. DevCon V4 stores a change at once as "not yet synced"; Sync sends it, with a reboot question; Discard changes; history; Restore defaults; Reboot. Save, open, download configuration and device URLs not verified | Update, Shots |
| `customer-environment/geofences` | Geofences | 2025-03-22 | Create, route, sites, connect devices, message | V4: circle, polygon and route, address search, attendance "Present and connected / Absent or disconnected". App: geofences show in the app under Groups > Locations | Update, Shots |
| `customer-environment/quick-texts` | Quick texts | 2021-12-23 | Make, edit, delete | Not mounted for V4-only accounts (`/quickTexts` redirects to the dashboard) | Wait T4 (keep for V3 accounts, add a V4 note) |
| `customer-environment/scenarios` | Scenarios | 2026-07-09 | Create, edit, test, webhooks, assistance requests | V4: cards with trigger, number of actions and "Last run"; side panel editor; nothing is stored until the save icon (the new card shows before saving). Example credentials question (see top) | Update, Shots |
| `customer-environment/scenarios/actions` | Scenario actions | 2026-06-02 | All actions, webhook body, placeholders | V4 dev lists 10 actions: Call webhook, Change team, Email, Multi tenant, Sms message, Send assistance request, Send last on-screen message again, Text message on device, Toggle timer alarm, Voice message. Not listed on dev: Show at alerts page, Start tracking, Change geofence presence, Create generic alarm, Send to ARC, Set digital I/O (may depend on modules or devices, unverified). Add "For concerning device", "Also send to app users who are offline", the `{{time}}` style placeholders | Update, Shots |
| `customer-environment/scenarios/triggers` | Scenario triggers | 2025-12-02 | All triggers, inverted triggers table | V4 dev lists 21 triggers. New or renamed: Low priority alarm, Geofence attendance, Enter geofence, Exit geofence, Too little turnout, Message not acknowledged, Quick button (linked from a custom view tile). Not listed on dev: Generic alarm, ARC alarm, Assistance request closed, Idle, Beacon battery, SMS message, Webhook, I/O change, ESPA message, Email (may depend on devices and modules, unverified). Keep the inversion table | Update |
| `customer-environment/scenarios/webhook-signature` | Webhook signature | 2026-07-09 | HMAC signature, code examples | Call webhook is a V4 action; signature not checked by Tess | Keep |
| `customer-environment/teams` | Teams | 2021-12-23 | Create, edit, delete, message | V4 team card screenshot exists; teams are recipients and show in the app under Groups > Teams with member status | Update, Shots |
| `customer-environment/users` | Users | 2025-07-01 | 2FA, roles, app licenses, welcome mails | V4: per-user permissions dialog (Full access, or Read, Update, Manage on 25 subjects, plus "Other permissions"); no standard roles; no app licenses (the V4 app is added as a Mobile App Lite device). 2FA, welcome mails, bulk actions not verified | Update, Shots, Wait T4 |

## Reseller environment

| Page | Title | Updated | Covers | V4 change | Action |
|---|---|---|---|---|---|
| `reseller-environment` | Reseller environment | 2025-07-01 | Intro | V4 menu: Accounts, Account management, Devices, Sites, Beacons, Users, About, Wiki, My account (items depend on permissions) | Update |
| `reseller-environment/account-management` | Account management | 2025-07-01 | Add, edit, login, alarm center, archive, delete | V4: choose Account or Sub-account manager; Users access list; Location maximum validity; Alarm auto-close after; no Timezone, App licenses or Modules (yet); login is an arrow icon, leaving is "Back to admin"; Account management tree; archive confirmation text. Draft: `support-staging/articles/reseller-environment/account-management.md` | Update, Shots |
| `reseller-environment/account-management/modules` | Account modules | 2025-07-01 | V3 module list | No modules in V4 yet (F1, v4-platform#468; proposal 006 is a direction, not built). Keep for V3 accounts, add a V4 note | Update (short V4 note), rewrite once modules are decided |
| `reseller-environment/beacon-management` | Beacon management | 2025-07-01 | Add beacon, types, battery reset | Beacons is in the V4 menu; not verified | Update, Shots (wiki report: V4 beacon types, beacons at position 0,0 on the map) |
| `reseller-environment/device-management` | Device management | 2025-10-28 | Add, edit, manage, first connection, ARC, bulk, labels | V4: 40 device types; Mobile App Lite with select or create user; Import devices from `template-devices.xlsx`; Manage sections (Communication and Receive settings "coming soon"); Replace device; devices cannot be added from inside a customer account. Mentions "disable the Presentation mode" for ARC scenarios | Update, Shots, Wait T1 |
| `reseller-environment/financial` | Financial | 2025-07-01 | Rates | Depends on permissions in V4; not verified | Keep, check (unverified) |
| `reseller-environment/reports` | Reports | 2025-07-01 | "Coming soon" only | Empty page | Remove until there is content |
| `reseller-environment/sim-card-management` | SIM card management | 2025-07-01 | SIM overview, manage, alerts | Depends on permissions in V4; not verified | Keep, check (unverified) |
| `reseller-environment/site-management` | Site management | 2026-03-09 | Add site, manage, beacons | Sites is in the V4 menu (screenshot `platform-v4/account-manager/04-new-site.png`); details not verified | Keep, Shots, check |
| `reseller-environment/translations` | Translations | 2025-07-01 | Edit translations | Depends on permissions in V4; not verified | Update (wiki report: V4 uses the platform's Translations page and the locale service; the Google Translate remark is outdated) |
| `reseller-environment/user-management` | User management | 2025-07-01 | Add user, edit, reset, welcome, bulk | V4: New user with first name, last name, email, Inform user by email, and a list of sub-accounts the user can also access; user menu Permissions, Reset password, Delete; a new sub-account manager starts without users | Update, Shots |

## Cuebly app

| Page | Title | Updated | Covers | V4 change | Action |
|---|---|---|---|---|---|
| `cuebly-app` | Cuebly app | 2025-07-01 | App states, heartbeat, OS versions, whitelabel, onboarding links | Concept of states still useful. Add: availability switch, timer alarm, Groups (teams, locations), language and theme, views. The V4 app is added as a Mobile App Lite device. OS version minimums not verified | Update, Shots |
| `cuebly-app/assistance-requests` | Assistance requests | 2025-07-01 | Show and make assistance requests in the legacy app | Not seen in the new app 1.4.0 | Wait T4 (legacy app only for now) |
| `cuebly-app/e-b10` | Connect e-B10 to the Cuebly app | 2025-07-01 | Pair the e-B10 button in the legacy app | No peripheral devices menu seen in the new app | Wait T4 (legacy app only for now) |
| `cuebly-app/faq` | FAQ mobile | 2025-07-01 | Permanent Android notification | New app also has a foreground notification: "Cue is checking configured geofences". Update the wording | Update |
| `cuebly-app/geofencing` | App geofencing | 2025-07-01 | Configure in "App settings", manual geofencing, enable or disable app in a geofence | New app: assigned geofences under Groups > Locations; automatic detection by an Android foreground service; no manual presence button seen; DevCon V4 has no geofencing section for Mobile App Lite | Update, Shots |
| `cuebly-app/onboarding` | Onboarding | 2025-07-01 | Legacy permission flow and the reasons | New flow: Welcome, Location ("Allow all the time"), Notifications, Critical alerts (Android), Microphone, Background activity, summary. Keep the "why" texts | Update, Shots |
| `cuebly-app/settings` | Mobile app settings | 2025-07-01 | Legacy settings via the menu icon | Settings is a tab in the bottom bar: user, email and device number; Availability; permission status; Set timer alarm; Language; Theme; Logout; Version. Inactivity alarm and sound settings not seen in 1.4.0 | Update, Shots |
| `cuebly-app/whitelabel` | Whitelabel your own Cuebly app | 2024-12-09 | Own store listing setup | Product notes: one generic app that shows the account's branding after login | Remove or replace (Jarno to confirm) |

## Supported devices

All device pages have a "Configuration options" table that describes the configurator. V4 and Emerit devices now open DevCon V4, other devices the legacy DevCon. The tables need a check against DevCon V4 per device, which is Tess's work (T4) or a later task.

| Page | Title | Updated | Action |
|---|---|---|---|
| `supported-devices/personal-trackers` | Personal alarms | 2025-09-23 | Update: add Mobile App Lite (the V4 app) as a device type; compare the list with the 40 types in V4 Devices > Add (unverified) |
| `supported-devices/personal-trackers/emerit-connect` | Emerit Connect App | 2025-07-01 | Keep (the V4 add form asks for the BLE Button MAC and says the device must be released from other Emerit Services accounts, which matches) |
| `supported-devices/personal-trackers/emerit-ewg100` | Emerit e-WG100 | 2026-02-03 | Keep, check DevCon V4 |
| `supported-devices/personal-trackers/emerit-ewg200` | Emerit e-WG200 | 2026-02-03 | Keep, check DevCon V4 |
| `supported-devices/personal-trackers/eview` | Eview GPS | 2025-07-01 | Merge into `eview/ev-04` (the parent page has 29 words) |
| `supported-devices/personal-trackers/eview/ev-04` | EV-04 | 2025-07-01 | Keep, check DevCon V4 (groups seen on dev: General, Wifi, Sound, Man down, Alarm numbers, Trusted numbers, Periodic positioning) |
| `supported-devices/personal-trackers/queclink` | Queclink | 2025-07-01 | Merge into `queclink/GL320MG` (parent has 28 words) |
| `supported-devices/personal-trackers/queclink/GL320MG` | GL320MG | 2025-07-01 | Keep |
| `supported-devices/personal-trackers/teltonika-gh5200` | Teltonika GH5200 | 2022-07-27 | Keep, check (oldest device page) |
| `supported-devices/personal-trackers/teltonika-tmt250` | Teltonika TMT250 | 2025-07-01 | Keep |
| `supported-devices/personal-trackers/twig` | TWIG (MPTP protocol, firmware) | 2025-04-10 | Keep |
| `supported-devices/personal-trackers/twig-easy` | Twig Easy | 2025-07-01 | Keep |
| `supported-devices/personal-trackers/twig-embody` | Twig Embody | 2024-02-06 | Keep, check: ripcord |
| `supported-devices/personal-trackers/twig-eon` | Twig Eon | 2025-10-21 | Keep |
| `supported-devices/personal-trackers/twig-neo` | Twig Neo | 2024-02-06 | Keep, check: ripcord; the import template calls it "20 - Twig Neo", the device list "Twig Neo 5" |
| `supported-devices/personal-trackers/twig-one` | Twig One | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-one-ex` | Twig One Ex | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-protector` | Twig Protector | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-protector-ex` | Twig Protector Ex | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-protector-pro` | Twig Protector Pro | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-protector-pro-ex` | Twig Protector Pro Ex | 2024-02-06 | Keep |
| `supported-devices/personal-trackers/twig-sos-card` | Twig SOS card | 2024-02-06 | Keep, check: ripcord (SOS card and SOS card P5 have one) |
| `supported-devices/gateways` | Gateways | 2025-07-01 | Keep |
| `supported-devices/gateways/elexol-ip2espa-v1` | IPtoESPA444 v1 | 2025-07-01 | Keep (ESPA2 cannot be imported from a file in V4; add one line on the device management page, not here) |
| `supported-devices/gateways/elexol-ip2espa-v2` | IPtoESPA444 V2 | 2025-09-25 | Keep |
| `supported-devices/gateways/teltonika-fmc640` | Teltonika FMC640 | 2025-07-01 | Keep |
| `supported-devices/gateways/teltonika-fmc650` | Teltonika FMC650 | 2025-07-01 | Keep |

Twig rule worth a line on every Twig page (Tess, code): only Twig Embody, Neo, SOS card and SOS card P5 have a ripcord.

## Integrations

| Page | Title | Updated | Covers | V4 change | Action |
|---|---|---|---|---|---|
| `integrations/arcs` | Alarm Receiving Centers | 2025-07-01 | What ARCs do, connect account and device | "Manage alarm center" is in the V4 row menus for accounts and devices (verified). Rest not verified | Keep, Shots |
| `integrations/arcs/securitas-communicator` | Securitas Communicator | 2024-04-26 | Data sent | Not product UI | Keep |

## Operations (internal)

| Page | Title | Updated | Action |
|---|---|---|---|
| `operations/CRM` | CRM | 2026-06-09 | Restrict |
| `operations/financial` | Financial operations | 2025-07-01 | Restrict |
| `operations/other` | Other | 2025-07-01 | Restrict |
| `operations/platform` | Platform | 2025-07-01 | Restrict |
| `operations/telecom` | Telecom | 2024-12-17 | Restrict |

## Merge

- `supported-devices/personal-trackers/eview` into `eview/ev-04` (or make the parent a short list page).
- `supported-devices/personal-trackers/queclink` into `queclink/GL320MG`.
- Presentation pages: the text sits in both `dashboards` and `alerts`. Once T1 is done, one page explains presentation pages and presentation mode, and the others link to it.

## Remove or replace

- `about-cuebly` (title only) unless Jarno wants a company page.
- `reseller-environment/reports` ("Coming soon" only).
- `cuebly-app/whitelabel`: replace with a short page "Your brand in the Cuebly app" once Jarno confirms the one-app-with-branding model.

## New pages to write

In the wiki's own structure. Status: `draft` means a Markdown draft exists in `support-staging/articles/`.

| # | Path | Title | Source | Status |
|---|---|---|---|---|
| N1 | `reseller-environment/presentation-mode` | Presentation mode | presentation-mode.md (T1) | Draft |
| N2 | `reseller-environment/device-management/add-app-user` | Add an app user (Mobile App Lite) | devices.md, mobile-app.md | Draft |
| N3 | `cuebly-app/timer-alarm` | Timer alarm | fact sheet, mobile-app.md | Draft |
| N4 | `cuebly-app/availability-presence` | Availability, presence and connection | glossary, fact sheet | Draft |
| N5 | `customer-environment/devices/devcon` | Change device settings (DevCon) | devices.md | Draft |
| N6 | `customer-environment/devices/custom-views` | Custom views and quick buttons in the app | devices.md, scenarios.md | Later: held until custom views show without the hidden switch (B14, B20) |
| N7 | `reseller-environment/account-management/sub-account-managers` | Sub-account managers | account-management.md | Part of the account management draft |
| N8 | `reseller-environment/device-management/import-devices` | Import devices from a file | devices.md | Draft |
| N9 | `customer-environment/users/permissions` | User permissions | account-management.md, wiki report | Next: V3 roles are replaced by permissions per subject (wiki report); proposal 006 may add roles later |
| N10 | `cuebly-app/groups` | Teams and locations in the app | mobile-app.md | Later (can be part of the `cuebly-app` rewrite) |
| N11 | `home/whats-new-in-v4` | What is new in V4 | all of the above | Later, after the first rewrites |
| N12 | `cuebly-app/send-help` | Send an alarm with the app (SOS button, SOS shortcuts, Samsung XCover side button) | fact sheet, mobile-app.md, wiki report | Later: needs Tess's details on SOS shortcuts |
| N15 | `supported-devices/personal-trackers/eview` (rewrite as overview) | Eview EV-04, EV-06, EV-07B, EV-12 | wiki report, V4 device types | Later: needs device facts |
| N16 | `supported-devices/personal-trackers/...` | Twig Neo Ex, Twig remote button, Emerit e-RG360 | wiki report | Later: needs device facts |
| N17 | `supported-devices/gateways/...` | Ajax hub and wall alarm, Moxa IO, generic device | wiki report | Later: needs device facts |
| N18 | `cuebly-app/messages` | Messages in the app | wiki report, proposal 009 | Later, after proposal 009 |
| N19 | `reseller-environment/alarm-center-management` | Alarm receiving centre management (links per account and device, pills in lists) | wiki report | Later: needs Tess's steps |
| N13 | `customer-environment/alerts/closing-script` | Close an alarm with the closing script (V4) | alerts.md | Draft (as a rewrite of `alerts/script`) |
| N14 | `customer-environment/scenarios/quick-button` | Start a scenario with a quick button | scenarios.md | Later, with N6 |

## Suggested order

Updated with Tess's order (wiki report):

1. Restrict the operations pages and remove the empty pages (Jarno).
2. New pages: add an app user (draft), presentation mode (draft), DevCon V4 (draft). Publish the device management ARC correction together with presentation mode.
3. App pages: onboarding and settings (drafts), then geofencing, timer alarm, availability and presence (drafts).
4. Customer environment: users (permissions, N9), scenario triggers and actions ("as seen on V4 dev"), alerts and the closing script (draft).
5. Reseller: account management (draft), device management full rewrite, import devices (draft).
6. Supported devices: missing V4 types (N15 to N17) and supported languages (draft).
7. Screenshots for each rewritten page, requested from Art per article.

## Open questions

Answered by Tess in the wiki report: see the table "Answers to David's questions" in frontend-design `knowledge/wiki-report.md`. Still open:

For Jarno:
- Restrict the operations pages, and confirm the example webhook credentials are dummies.
- Do Quick texts, Alarm protocols and Assistance requests pages come back for V4 accounts?
- Do the scenario triggers and actions missing on dev depend on devices or modules?
- What do the closing script outcomes lead to?
- Presentation mode: should V4 hide scenarios again, should the choice be remembered after reload, what should a customer see when every DevCon group is hidden?
- Keep the V3 pages for V3 customers during the change, or replace them? Advice: keep one wiki, and add a short "In V4" note on pages that differ, until all customers are on V4.
- `about-cuebly`: remove, or write a short company page?
- `cuebly-app/whitelabel`: replace with the one-app-with-branding explanation?

For Tess:
- SOS shortcuts and the XCover side button: exact options and steps (for N12).
- Adoption of an account and alarm centre management: steps (for account management and N19).
- Financial, SIM card management and Reports for a login with those permissions.
