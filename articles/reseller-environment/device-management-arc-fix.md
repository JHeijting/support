---
path: reseller-environment/device-management
title: Device management (correction: ARC scenario)
section: Connect a device to your alarm receiving center (ARC), last part
type: correction (replace one passage on the live page; the full page rewrite comes later)
status: check
sources: frontend-design knowledge/modules/presentation-mode.md (scenarios cannot be hidden), Tess T13 answers 2026-10-21 (code: Send alarm to ARC, ARC-link scenario), wiki-report.md (device-management row)
last fact check: 2026-10-22
author: David van der Berg
---

# Correction: ARC scenario and presentation mode

## Remove this passage from the live page

> Lastly, to enable the actual action, you should create a ARC scenario in the customer environment. So the first step is to login as your customer.
> Go to the "Scenarios" page. Be sure to disable the "Presentation mode" on the left-bottom side of the page.
> By default, an ARC scenario will be created that is not visible for the customer, but you could create your own or one extra.
> Make sure the scenario has an alarm trigger and a "Send to alarm center" scenario action included.
> Only connected devices will then be used in this scenario action.

## Replace it with

> Lastly, the alarms must be sent to the ARC by a scenario in the customer environment.
>
> 1. Log in to the customer environment. See [Account management](/i/34).
> 2. Go to **Scenarios**. Linking the ARC creates a scenario with the action **Send alarm to ARC**. Check that it is there and enabled. To make your own, use an alarm trigger (or **Connection changed**) and add **Send alarm to ARC**; a scenario can have this action once. Only devices that are connected to the ARC are used by this action. [unverified: read in the code, not yet seen live]
>
> Scenarios cannot be hidden from the customer. The customer sees this scenario in their own **Scenarios** list. You do not need to switch off presentation mode to see it. See [Presentation mode](/i/115).

---

## Draft notes (remove before publishing)

- **The ARC action:** Tess (T13, code): the action is "Send alarm to ARC" (`send_to_arc`), offered only with an alarm trigger or "connection changed", once per scenario; linking an ARC creates an ARC-link scenario with it. Not seen live (no ARC on her accounts). Before publishing: one check on an account with an ARC linked (scenario name and that it is enabled). Whether "only connected devices" still holds is not covered by her answer.
- The rest of the device management page is planned as a full rewrite (inventory: Wi-Fi only, Cuebly SIM with ICCID, import, power off and reboot, DevCon V4).
