---
path: customer-environment/dashboards
title: Dashboards
description: The dashboard of a customer environment
replaces: customer-environment/dashboards (2025-07-01)
status: check
sources: frontend-design knowledge/modules/dashboard.md, wiki-report.md (dashboards row: custom dashboards not in V4 yet, Jarno), presentation-mode.md (presentation pages are not presentation mode)
last fact check: 2026-10-21
author: David van der Berg
---

# Dashboards

The **Dashboard** is the first page of a customer environment. It shows the state of the account at a glance.

## The default dashboard

Every account starts with the **Default dashboard**, with these tiles:

- **Open alarms**: how many alarms are not closed yet.
- **Open alerts** [see draft notes]
- **Days without alarms**: how many days since the last alarm.

![The default dashboard of a customer account. Marker 1 points at the dashboard picker showing Default dashboard, marker 2 at the tiles Open alarms, Open alerts and Days without alarms, each with its count.](/wiki-images/dashboards/dashboards-01-default-dashboard.png)
*The dashboard opens with the Default dashboard (1). Its tiles show open alarms, open alerts and the days without alarms (2).*

## Custom dashboards

Custom dashboards, with your own tiles, are not available. [see draft notes]

## Presentation pages are not presentation mode

A **presentation page** shows dashboards as a slideshow, for example on a screen on the wall. **Presentation mode** is something else: it lets an account manager see an account the way the customer sees it. See [Presentation mode](/i/115).

---

## Draft notes (remove before publishing)

- **Conflicting sources:** Jarno says custom dashboards are not in V4 yet; Tess saw a "Default dashboard" drop-down with a `+` and a Dashboard library with 16 tiles on dev (dashboard.md). Jarno to decide what the page says. If custom dashboards are in V4, this page gets the full flow: picker, `+`, Add tile, Dashboard library, Configure with size Small, Medium, Large, the orange "This tile needs to be configured" badge, and the module request for the Enable or disable scenarios tile.
- **Open alarms versus Open alerts:** the difference is not explained (B32). Explain or drop the second tile once known.
- **Presentation pages in V4:** not verified; the section only explains the difference.
- **Images:** Art's `dashboards/dashboards-01-default-dashboard.png`.
