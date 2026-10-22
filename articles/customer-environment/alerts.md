---
path: customer-environment/alerts
title: Alerts
description: See incoming alarms, handle them and close them
replaces: customer-environment/alerts (2024-12-19)
status: check
sources: frontend-design knowledge/modules/alerts.md (night test 2026-10-21), Tess T13 answers 2026-10-21 (tested: alarm card, right pane, Quick close), wiki-report.md (alerts row), glossary.md; sound and browser notification text kept from the previous wiki page
last fact check: 2026-10-22
author: David van der Berg
---

# Alerts

**Alerts** is where alarms come in. Here you see what happened, handle the alarm and close it. The number next to **Alerts** in the menu shows how many alarms are open.

![The Alerts page with the list of open alerts. Marker 1 points at Alerts in the left menu with a count badge, marker 2 at an open Timer alarm in the list.](/wiki-images/handle-an-alarm/handle-an-alarm-01-open-alerts.png)
*Open Alerts (1). The badge shows the number of open alarms. Click an alarm in Open alerts (2) to see its details.*

![Flow from an alarm in the Cuebly app to a closed alarm, in three lanes. Cuebly app: hold Send help! for 3 seconds, or a timer alarm runs out; the app shows "Alarm is sent" and the alarm goes to the platform. Platform: the alarm appears in Alerts and can start scenarios; alarms not closed by hand close automatically after a set number of days (default 30). Operator: Close alarm, then the closing script (alarm type, Start alarm handling, call the device, outcome, notes) or Quick close; the closed alarm shows the time to close and the notes.](/wiki-images/diagrams/diagrams-01-alarm-flow.png)
*How an alarm from the app is handled and closed.*

## The list

- **Open alerts**: alarms that are not closed yet. New alarms appear at once.
- **Closed alerts**: alarms that were closed.

Each alarm shows its type (for example **SOS button** or **Timer**), the device and the time. The map on the right shows where the devices are.

## Open an alarm

Click an alarm. The alarm card in the middle shows:

- its status and type, with **Close alarm**,
- **Voice connection available** with **Join the call**, when the device has started a voice connection,
- a map (**Enlarge** makes it bigger; "No location information available" when there is none),
- the device, the time of the alarm, and the last location with the time it was received and the time it was determined,
- the device fields, such as phone number, operating address, industry and alarm protocol.

The pane on the right shows:

- **Create assistance request**, to ask others for help (name, devices, teams, geofences, message, language),
- **What happened**, a timeline of the alarm: for example location fixed, alarm raised, alarm closed with the note.

## Close an alarm

Click **Close alarm** and choose:

- **Start closing script**: a step-by-step guide that records the outcome and the time to close. See [Close an alarm with the closing script](/i/94).
- **Quick close**: close the alarm at once. Fill in **What actions did you do?** (required).

### Close several alarms at once

1. Under **Open alerts**, tick the alarms, or use **Select all**.
2. Click the check icon at the top of the list.

The selected alarms are closed.

## Close alarms automatically

At the top of **Alerts**, **Alarm auto-close after** shows after how long alarms that nobody closed are closed automatically. The default is 30 days. Your account manager can change the period for your account.

## Sound

The speaker icon at the top of **Alerts** switches the alarm sound on or off. [unverified]

If you do not hear alarms while the browser is in the background, see [FAQ - Web](/i/105).

---

## Draft notes (remove before publishing)

**Removed from the page (wiki rule: current product only, Jarno 2026-10-21). Kept here for the cutover plan:**

- Alarms from scenarios with the action **Show at alerts page** no longer exist; that action is gone.

- **Bulk close without note or confirmation** (B21, development/docs/v4-platform#476): a gap, left out of the text. The check icon also has no label. Describe the intended flow (notes, confirmation) once fixed.
- **Who may change auto-close:** the header shows it on the Alerts page, the account setting is on Edit account (account manager). Whether a customer user can change it from the Alerts header is not verified; Tess's screenshot shows a drop-down. Check.
- **Share alert by email, browser notifications, presentation page of open alerts:** V3 features, not verified in V4. Left out.
- **Alarms closed by an ARC:** not verified in V4. Left out.
- **"Open alarms" and "Open alerts"** dashboard tiles: difference unexplained (B32). Not mentioned.
- **Response pane:** tested by Tess (T13, 2026-10-21 23:26 to 23:33 CEST, SOS from the app), now in the text.
- **Assistance request from an alarm** (v4-platform#461): a request made from the alarm shows as a separate alert and is not closed with the alarm. Jarno: assistance requests will be merged into alarms (Q9). Left out of the text until that is built.
- **Images:** Art's `handle-an-alarm/handle-an-alarm-01-open-alerts.png`; auto-close and bulk close have no image yet (T7).
- Diagram `diagrams-01-alarm-flow.png` (Q11: diagrams welcome). Its own check list: it stops at Closed (follow-up protocol not in V4 yet) and does not draw app feedback (F8).
