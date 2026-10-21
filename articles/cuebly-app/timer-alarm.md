---
path: cuebly-app/timer-alarm
title: Timer alarm
description: Set a timer in the Cuebly app that raises an alarm if you do not cancel it in time
status: check
sources: frontend-design knowledge/2026-10-21-fact-sheet-v4-and-app.md, modules/mobile-app.md, glossary.md (night test, app 1.4.0, 2026-10-21)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Timer alarm

Use the timer alarm when you go into a situation where you might not be able to call for help yourself, for example a visit alone, work at height or a walk to the car park at night. You set how long you expect it to take. If you do not cancel the timer in time, the app raises an alarm.

## Start a timer

1. Open **Settings** in the bottom bar.
2. Tap **Set timer alarm**.
3. Choose a duration with the dial, or tap **30m**, **1h**, **2h** or **6h**. You can choose from 1 minute to 6 hours.
4. Tap **Start timer**.

A banner on the **Home** screen shows the time left.

![The timer screen with the dial and the quick choices](image: timer-alarm-01-set-timer)

## Cancel the timer

When you are safe, tap **Cancel** on the banner on the **Home** screen. The timer stops at once.

![The home screen of the Cuebly app. Marker 1 points at the large red Send help! button, marker 2 at the Status card with the Available switch, marker 3 at a running SOS Timer banner with 23:54 left and a Cancel button, marker 4 at the bottom bar with Home, Groups, Views and Settings.](/wiki-images/cuebly-app/cuebly-app-02-home.png)
*Hold Send help! for 3 seconds to send an alarm (1). Switch your availability under Status (2). A running timer alarm shows at the top, with Cancel (3). The bottom bar (4) leads to Groups, Views and Settings.*

## What happens when time runs out

1. **One minute before the end**, the app shows a notification that asks you to cancel the timer if you are OK.
2. **At the end**, the app sends a **Timer** alarm to the platform.
3. The alarm appears in **Alerts** in the customer environment, with the device and the time, and can start scenarios with the trigger **Timer**.

## For administrators

- A timer alarm is an alarm like any other. Handle it in **Alerts**, and use the scenario trigger **Timer** to warn colleagues or an alarm receiving centre.
- A scenario can also start or stop the timer on a device with the action **Toggle timer alarm**.
- In DevCon V4, the feature **Timer alarm** has two switches per app device: **Enabled** (whether the timer is on when the app starts) and **Change device configuration** (whether the user may change it in the app). [unverified: what the user sees when it is off]

---

## Draft notes (remove before publishing)

- **Known issues in app 1.4.0** (keep out of the article, check before publishing):
  - The pre-alarm notification text is hard-coded English ("SOS Timer Alert ... Cancel now if you are OK", B16). The article does not quote it.
  - The timer screen itself does not show a running timer (B15); cancel is on the Home banner. If B15 is fixed, add "or open Set timer alarm again".
  - The banner covers the header (F9).
  - When the alarm goes, the app shows nothing to the user (F8). Do not promise feedback in the app.
- **Where the timer lives:** Settings > Set timer alarm today. Proposal 008 (timer placement) may move it; update when built.
- **DevCon V4 feature Timer alarm:** meaning of both switches answered in the wiki report. Tess saw "Set timer alarm" still shown in the app with the setting hidden (presentation mode screenshot 07).
- **Presentation mode:** with Timer alarm hidden, the app still shows Set timer alarm. Left out of the text (gap, see presentation mode notes and Q10).
- **Images:** requested from Art (timer-alarm-01, 02). Source screenshots: `current/app-v4/09-timer-nl.png` (Dutch, an English one is needed), `current/app-v4/10-timer-banner-en.png`.
- **Diagram (optional, Q11):** Art's `wiki-images/diagrams/diagrams-01-alarm-flow.png`. Only if Jarno allows concept diagrams on the wiki (they are not screenshots).
