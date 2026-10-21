---
path: customer-environment/scenarios
title: Scenarios
description: Let the platform act automatically when something happens
replaces: customer-environment/scenarios (2026-07-09)
status: check
sources: frontend-design knowledge/modules/scenarios.md (night test 2026-10-21), presentation-mode.md (scenarios cannot be hidden), wiki-report.md; webhook and assistance request follow-up kept from the previous wiki page
last fact check: 2026-10-21
author: David van der Berg
---

# Scenarios

A scenario is a rule: **when** something happens, the platform **does** one or more things. For example: when someone sends an SOS from the app, send a message to everyone present in the same building.

- What starts a scenario: see [Scenario triggers](/en/customer-environment/scenarios/triggers).
- What a scenario can do: see [Scenario actions](/en/customer-environment/scenarios/actions).

## The scenario list

Go to **Scenarios**. Each scenario is a card with its trigger, the number of actions and when it last ran ("Last run"). Use **Filter by device** to find the scenarios of one device.

## Create a scenario

1. Go to **Scenarios** and click **New scenario** (the round button).
2. Check that **Enabled** is on.
3. Under **General**, name the scenario. Choose whether it is **Always available** or only at set times with **Manage schedule**.
4. Under **When this happens**, choose the trigger.
5. Under **Configure trigger**, set its options and click **Next**.
6. Under **Perform these actions**, click **New action** and choose an action. Set it up. Add more actions if needed.
7. Click the save icon at the top of the panel. "Scenario saved" appears.

![The Scenarios page with one scenario card. Marker 1 points at Scenarios in the left menu, marker 2 at the New scenario button at the bottom of the list.](/wiki-images/create-a-scenario/create-a-scenario-01-new-scenario.png)
*Open Scenarios (1) and click New scenario (2). The editor opens on the right.*

![The scenario editor with the trigger list open. Marker 1 points at the Enabled switch, marker 2 at General where you name the scenario, marker 3 at the Trigger field. The list shows the personal alarms Any alarm, Low priority alarm, SOS button, Man down, Ripcord, Timer and Alarm closed, followed by device status triggers.](/wiki-images/create-a-scenario/create-a-scenario-02-choose-trigger.png)
*Check that the scenario is Enabled (1), give it a name under General (2), then choose under When this happens what starts it (3).*

![The scenario editor with the Quick button trigger chosen. Marker 1 points at When this happens, set to Quick button. Marker 2 points at Configure trigger, which says to select this scenario in the device configurator. Marker 3 points at the list of actions: Call webhook, Change team, Email, Multi tenant, Sms message, Send assistance request, Send last on-screen message again, Text message on device, Toggle timer alarm and Voice message.](/wiki-images/create-a-scenario/create-a-scenario-03-add-action.png)
*The chosen trigger shows under When this happens (1). Set its options under Configure trigger (2) and click Next. Under Perform these actions, click New action and choose what the scenario does (3).*

The scenario is stored when you click the save icon.

## Change, disable or delete a scenario

Click the scenario card to open it. Change what you need and click the save icon.

- **Disable**: switch **Enabled** off and save. [unverified: Delete and Copy in V4]

## Test an action

Open the action and click **Test action**. The action runs once, without the trigger. [unverified: whether the test is marked as a test]

## Quick buttons

A scenario with the trigger **Quick button** is started from a tile in the Cuebly app. You link the tile to the scenario in the device's custom view in DevCon V4, not in the scenario. See [Change device settings (DevCon V4)](/en/customer-environment/devices/devcon-v4).

## Who sees the scenarios

All users with access to scenarios see all scenarios of the account. In V4 a scenario cannot be hidden from the customer, also not by an account manager. See [Presentation mode](/en/reseller-environment/presentation-mode).

## Webhooks

To send events to your own system, use the action **Call webhook**. To check that a request comes from Cuebly, see [Webhook signature](/en/customer-environment/scenarios/webhook-signature).

---

## Draft notes (remove before publishing)

- **Removed from the old page:** the webhook trigger example with client id and secret (Q5: confirm they are dummies, and whether the Webhook trigger exists in V4; it is not in the 21 triggers on dev) and the "obsolete" authorization header example. Bring back only if the Webhook trigger is in V4.
- **Assistance request follow-up** (old page section) now sits in the actions page (Send assistance request, Too little turnout). Settings of that action not verified in V4.
- **Delete, Copy:** V3 features; not seen by Tess in the V4 editor. Verify.
- **Unsaved card** (night test): a new scenario shows as a card in the list before it is saved, and is lost on close without saving. A gap, left out of the text; ask Tess for the ticket id.
- **Empty list:** shows "Create a scenario" with an arrow pointing away from the button (B27). Not mentioned.
- **Images:** Art's `create-a-scenario` 01, 02, 03.
- **Diagram (optional, Q11):** Art's `wiki-images/diagrams/diagrams-02-scenario.png (trigger, configure, Enabled and schedule, actions)`. Only if Jarno allows concept diagrams on the wiki (they are not screenshots).
