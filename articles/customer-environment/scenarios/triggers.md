---
path: customer-environment/scenarios/triggers
title: Scenario triggers
description: The events that can start a scenario in Cuebly V4
replaces: customer-environment/scenarios/triggers (2025-12-02)
status: check
sources: frontend-design knowledge/modules/scenarios.md (21 triggers, night test 2026-10-21), wiki-report.md, screenshot current/platform-v4/scenarios/02-trigger-list.png; descriptions of unchanged triggers kept from the previous wiki page
last fact check: 2026-10-21
author: David van der Berg
---

# Scenario triggers

A scenario starts when its **trigger** happens. You choose one trigger per scenario under **When this happens**, then set its options under **Configure trigger**.

Which triggers you see depends on your account and its devices. The list below is what a standard customer account offers. [see draft notes]

## Personal alarms

| Trigger | Starts the scenario when |
|---|---|
| **Any alarm** | a selected device raises an alarm of any type |
| **Low priority alarm** | a selected device raises a low priority alarm [unverified: which alarms count as low priority] |
| **SOS button** | a selected device raises an SOS alarm, for example "Send help!" in the app |
| **Man down** | a selected device raises a man down alarm |
| **Ripcord** | the cord of a Twig device with a ripcord is pulled (Twig Embody, Neo, SOS card, SOS card P5) |
| **Timer** | a timer alarm runs out. See [Timer alarm](/i/124) |
| **Alarm closed** | an alarm of a selected device is closed |

## Device status

| Trigger | Starts the scenario when |
|---|---|
| **Config error** | a device fails to take over its configuration |
| **Connection change** | a device loses or gets back its connection with the platform |
| **Docked** | a device is put on its charger or docking station |
| **Undocked** | a device is taken off its charger or docking station |
| **Low battery** | a device reports a low battery |
| **No alarm triggered** | a device has not raised an alarm for a number of days (useful to remind people to test) |

## Locations

| Trigger | Starts the scenario when |
|---|---|
| **Enter geofence** | a device enters a geofence. Choose **Any geofence** or specific geofences |
| **Exit geofence** | a device leaves a geofence |
| **Geofence attendance** | the number of devices present in a geofence reaches a set level [unverified: options] |

## Follow-up

| Trigger | Starts the scenario when |
|---|---|
| **Message not acknowledged** | a text message sent by another scenario is not acknowledged in time. Link it from the **Text message on device** action |
| **Too little turnout for assistance request** | too few people accepted an assistance request in time. Link it from the **Send assistance request** action |

## Other

| Trigger | Starts the scenario when |
|---|---|
| **Quick button** | someone presses a quick button tile in the Cuebly app. This trigger has no settings in the scenario: you link it from the tile, in the device's custom view in DevCon |
| **Multi tenant** | a scenario in another customer account starts it, with the **Multi tenant** action |
| **Scenario disabled** | a selected scenario is disabled, by hand or automatically |

## Tips

- **Connection change:** set a timeout (for example 60 seconds), so a short network gap does not start the scenario. [unverified]
- **Inverting the selection:** some triggers let you start the scenario for every device except the selected ones. [add the table of examples] [unverified]

---

## Draft notes (remove before publishing)

**Removed from the page (wiki rule: current product only, Jarno 2026-10-21). Kept here for the cutover plan:**

Not offered in V4 for a standard account: Generic alarm, ARC alarm, Assistance request closed, Idle, Beacon battery, SMS message, Webhook, I/O change, ESPA message and Email. [see draft notes]

- **"As seen on V4 dev":** the 21 triggers are what V4 dev offers for Tess's test customer (wiki report). Jarno to confirm whether the missing V3 triggers depend on devices (gateways, ESPA, I/O) or modules, or are gone (Q8 area). Until then keep "for a standard customer account" and the "What changed" line, or drop that line.
- **Group names:** the screenshot shows "Personal alarms" and "Device status"; the other group names in V4 are not known. The draft uses its own headings for the rest; align with the real groups.
- **Descriptions** of unchanged triggers are kept from the V3 page. New ones (Low priority alarm, Geofence attendance) need Tess's check.
- **Inversion table:** the V3 page has a detailed example table. Keep it if inversion still exists in V4.
- **Images:** Art's `create-a-scenario/create-a-scenario-02-choose-trigger.png` fits the intro (not mapped yet, optional).
