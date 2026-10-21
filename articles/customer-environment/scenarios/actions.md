---
path: customer-environment/scenarios/actions
title: Scenario actions
description: What a scenario can do in Cuebly V4, and how to use placeholders
replaces: customer-environment/scenarios/actions (2026-06-02)
status: check
sources: frontend-design knowledge/modules/scenarios.md (10 actions, Text message on device in detail, night test 2026-10-21), wiki-report.md, screenshot current/platform-v4/scenarios/04-action-types.png; webhook body and placeholder explanations kept from the previous wiki page
last fact check: 2026-10-21
author: David van der Berg
---

# Scenario actions

When a scenario starts, it performs its **actions** one after the other. Add actions under **Perform these actions** with **New action**.

![The scenario editor with the Quick button trigger chosen. Marker 1 points at When this happens, set to Quick button. Marker 2 points at Configure trigger, which says to select this scenario in the device configurator. Marker 3 points at the list of actions: Call webhook, Change team, Email, Multi tenant, Sms message, Send assistance request, Send last on-screen message again, Text message on device, Toggle timer alarm and Voice message.](/wiki-images/create-a-scenario/create-a-scenario-03-add-action.png)
*The chosen trigger shows under When this happens (1). Set its options under Configure trigger (2) and click Next. Under Perform these actions, click New action and choose what the scenario does (3).*

An action with a lock icon is not active for your account. [unverified: what happens when you choose it; see draft notes]

## The actions

| Action | What it does |
|---|---|
| **Text message on device** | Shows a message on the screen of devices and in the Cuebly app |
| **Voice message** | Calls the recipients and reads out a message |
| **Sms message** | Sends a text message (SMS) to phone numbers |
| **Email** | Sends an email |
| **Send assistance request** | Asks people to help; they accept or reject in the app |
| **Send last on-screen message again** | Sends the last text message again to the device |
| **Change team** | Moves the device that started the scenario into or out of teams |
| **Toggle timer alarm** | Starts or stops the timer alarm on a device |
| **Call webhook** | Sends the event to another system over HTTP |
| **Multi tenant** | Starts a scenario in another customer account |

## Text message on device

1. Choose the **recipients**:
   - **Devices**: **All other devices**, **For concerning device** (the device that started the scenario), or named devices.
   - **Teams** and **Geofences**: everyone in those teams, or everyone present in those geofences.
2. Write the **message**. Click a placeholder to add live details, such as the time or the device name (see below).
3. Choose the **language** of the message.
4. Optional: tick **Also send to app users who are offline**.
5. Optional: choose a **follow-up scenario** that starts when the message is not acknowledged in time. That scenario uses the trigger **Message not acknowledged**.
6. Use **Test action** to try it without starting the scenario.

![The Text message on device action. Marker 1 points at the Devices field, marker 2 at the message text, marker 3 at the placeholders that can be added to the message, such as DATE, TIME and DEVICE, marker 4 at the language of the message, marker 5 at the save icon at the top of the editor.](/wiki-images/create-a-scenario/create-a-scenario-04-text-message-action.png)
*Choose who receives the message (1) and write it (2). Click a placeholder to add details such as the time or the device (3). Choose the language (4), then save the scenario with the icon at the top (5).*

Of the people present in a geofence, only app users who are **available** receive the message. See [Availability, presence and connection](/en/cuebly-app/availability-presence).

## Placeholders

Placeholders add live information to a message. You add them with a click; they show as a token such as `{{time}}`. Available placeholders:

| Placeholder | Shows |
|---|---|
| DATE, TIME | when the event happened |
| DEVICE | the name of the device |
| PHONE NUMBER | the phone number of the device |
| OPERATING ADDRESS, CUSTOM ADDRESS | the addresses set on the device |
| INDUSTRY, SITE | details of the device |
| GEOFENCE | for a geofence trigger: the geofence entered or left; otherwise the smallest geofence the device is in |
| GEOFENCES | the geofences the device is in |
| GOOGLE MAPS URL | a link to the location in Google Maps |
| LIVE LOCATION URL | a link to the live location of the device |

Device fields you added yourself are available as placeholders too.

**Be careful with LIVE LOCATION URL.** Anyone with the link can see where the person is while the link is valid (24 hours). [unverified in V4: link lifetime]

## Call webhook

Sends the event, with the device and its location, to your own system. For the request body and how to check that a request comes from Cuebly, see [Webhook signature](/en/customer-environment/scenarios/webhook-signature). [unverified: V4 body unchanged]

## What changed from V3

- **Show at alerts page** is gone. Alarms show in **Alerts** by themselves.
- Not offered in V4 for a standard account: Start tracking, Change geofence presence, Create generic alarm, Send to ARC and Set digital I/O. [see draft notes]

---

## Draft notes (remove before publishing)

- **"As seen on V4 dev":** 10 actions for Tess's test customer. Missing V3 actions may depend on devices or modules (Jarno, Q8 area). Send to ARC especially: see the device management ARC correction.
- **Lock icons:** in the screenshot Multi tenant, Sms message, Send assistance request and Voice message have a lock. On the dashboard, a locked tile opens "Activate module" with a request form (B42); for actions this is not verified. Proposal 006 drops the request flow. Describe once verified.
- **Placeholders** appear twice with raw names today (B30); the table uses the names from Tess's list.
- **Wait for possible new location** (V3 checkbox for location placeholders) not verified in V4; left out.
- **Voice message, Sms message, Email, Change team, Toggle timer alarm, Multi tenant:** descriptions from the V3 page, settings not documented by Tess.
- **"For concerning device"** did not show the message in the app in one geofence test (B36, to verify). Keep an eye on it before publishing.
- **Webhook example on the old Scenarios page:** see Q5 (credentials).
- **Images:** Art's `create-a-scenario/create-a-scenario-03-add-action.png` and `-04-text-message-action.png`.
- **Diagram (optional, Q11):** Art's `wiki-images/diagrams/diagrams-02-scenario.png`. Only if Jarno allows concept diagrams on the wiki (they are not screenshots).
