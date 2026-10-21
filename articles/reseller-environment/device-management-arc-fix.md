---
path: reseller-environment/device-management
title: Device management (correction: ARC scenario)
section: Connect a device to your alarm receiving center (ARC), last part
type: correction (replace one passage on the live page; the full page rewrite comes later)
status: check
sources: frontend-design knowledge/modules/presentation-mode.md (V4 scenarios cannot be hidden), wiki-report.md (device-management row)
last fact check: 2026-10-21
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
> 1. Log in to the customer environment. See [Account management](/en/reseller-environment/account-management).
> 2. Go to **Scenarios** and check that there is a scenario with an alarm trigger and the action that sends the alarm to the alarm center. Only devices that are connected to the ARC are used by this action. [unverified]
>
> Scenarios cannot be hidden from the customer. The customer sees this scenario in their own **Scenarios** list. You do not need to switch off presentation mode to see it. See [Presentation mode](/en/reseller-environment/presentation-mode).

---

## Draft notes (remove before publishing)

- **The ARC action in V4:** Tess counted 10 scenario actions on V4 dev for a test account, and "Send to ARC" / "Send to alarm center" is not one of them. It may depend on the account's ARC link or modules. Before publishing, check on an account with an ARC linked: is the ARC scenario still created by default, and what is the action called? If V4 sends alarms to the ARC without a scenario, drop the steps and keep only the presentation mode sentence.
- The rest of the device management page is planned as a full rewrite (inventory: Wi-Fi only, Cuebly SIM with ICCID, import, power off and reboot, DevCon V4).
