---
path: customer-environment/alerts
title: Alerts
description: See incoming alarms, handle them and close them
replaces: customer-environment/alerts (2024-12-19)
status: check
sources: frontend-design knowledge/modules/alerts.md (night test 2026-10-21), wiki-report.md (alerts row), glossary.md; sound and browser notification text kept from the previous wiki page
last fact check: 2026-10-21
author: David van der Berg
---

# Alerts

**Alerts** is where alarms come in. Here you see what happened, handle the alarm and close it. The number next to **Alerts** in the menu shows how many alarms are open.

![The Alerts page with the list of open alerts. Marker 1 points at Alerts in the left menu with a count badge, marker 2 at an open Timer alarm in the list.](/wiki-images/handle-an-alarm/handle-an-alarm-01-open-alerts.png)
*Open Alerts (1). The badge shows the number of open alarms. Click an alarm in Open alerts (2) to see its details.*

## The list

- **Open alerts**: alarms that are not closed yet. New alarms appear at once.
- **Closed alerts**: alarms that were closed.

Each alarm shows its type (for example **SOS button** or **Timer**), the device and the time. The map on the right shows where the devices are.

## Open an alarm

Click an alarm to see:

- its status, type and time,
- the device, its connection and last location, with a map ("No location information available" when there is none),
- the device fields, such as operating address and industry,
- **What happened**: a timeline of the alarm,
- whether an assistance request is linked to it.

## Close an alarm

Click **Close alarm** and choose:

- **Start closing script**: a step-by-step guide that records the outcome and the time to close. See [Close an alarm with the closing script](/en/customer-environment/alerts/script).
- **Quick close**: close the alarm at once, with notes. [unverified: notes on quick close]

### Close several alarms at once

1. Under **Open alerts**, tick the alarms, or use **Select all**.
2. Click the check icon at the top of the list.

The selected alarms are closed.

## Close alarms automatically

At the top of **Alerts**, **Alarm auto-close after** shows after how long alarms that nobody closed are closed automatically. The default is 30 days. Your account manager can change the period for your account.

## Sound

The speaker icon at the top of **Alerts** switches the alarm sound on or off. [unverified: V4 behaviour]

If you do not hear alarms while the browser is in the background, see [FAQ - Web](/en/customer-environment/faq).

## What changed from V3

- Alarms from scenarios with the action **Show at alerts page** no longer exist; that action is gone.

---

## Draft notes (remove before publishing)

- **Bulk close without note or confirmation** (B21, development/docs/v4-platform#476): a gap, left out of the text. The check icon also has no label. Describe the intended flow (notes, confirmation) once fixed.
- **Who may change auto-close:** the header shows it on the Alerts page, the account setting is on Edit account (account manager). Whether a customer user can change it from the Alerts header is not verified; Tess's screenshot shows a drop-down. Check.
- **Share alert by email, browser notifications, presentation page of open alerts:** V3 features, not verified in V4. Left out.
- **Alarms closed by an ARC:** not verified in V4. Left out.
- **"Open alarms" and "Open alerts"** dashboard tiles: difference unexplained (B32). Not mentioned.
- **Response pane** (wiki report: "describe the response pane"): not documented; ask Tess what it shows.
- **Images:** Art's `handle-an-alarm/handle-an-alarm-01-open-alerts.png`; auto-close and bulk close have no image yet (T7).
