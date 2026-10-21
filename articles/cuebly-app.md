---
path: cuebly-app
title: Cuebly app
description: The Cuebly app turns a smartphone into a personal safety device
replaces: cuebly-app (2025-07-01)
status: check
sources: frontend-design knowledge/modules/mobile-app.md, fact sheet 2026-10-21, glossary.md, wiki-report.md (cuebly-app row); app states and heartbeat kept from the previous wiki page
last fact check: 2026-10-21
author: David van der Berg
---

# Cuebly app

The Cuebly app turns an iPhone or Android phone into a personal safety device. The app user can ask for help with one button, set a timer alarm, and receive messages from the platform. In the customer environment, the app is a device like any other personal alarm.

## Get started

- **For account managers:** add the app as a device of the type Mobile App Lite. See [Add an app user](/en/reseller-environment/device-management/add-app-user).
- **For app users:** install the app, log in with the details from the welcome email and follow the [onboarding](/en/cuebly-app/onboarding).

There is one Cuebly app for everyone. After login, the app shows the branding of your organisation. [unverified with a partner brand]

## What is in the app

The bottom bar has:

- **Home**: the **Send help!** button, the **Available** switch and, when a timer runs, the timer banner.
- **Groups**: your **Teams**, with their members and whether they are available, and your **Locations** (geofences), with a map and who is present.
- **Views**: pages with tiles set up by your administrator, for example a quick button that starts a scenario, or instructions. Only shown when your administrator set up custom views. [see draft notes]
- **Settings**: availability, permissions, timer alarm, language, theme and logout. See [App settings](/en/cuebly-app/settings).

![The home screen of the Cuebly app. Marker 1 points at the large red Send help! button, marker 2 at the Status card with the Available switch, marker 3 at a running SOS Timer banner with 23:54 left and a Cancel button, marker 4 at the bottom bar with Home, Groups, Views and Settings.](/wiki-images/cuebly-app/cuebly-app-02-home.png)
*Hold Send help! for 3 seconds to send an alarm (1). Switch your availability under Status (2). A running timer alarm shows at the top, with Cancel (3). The bottom bar (4) leads to Groups, Views and Settings.*

## What you can do

- **Ask for help:** hold **Send help!** for 3 seconds. See [Send an alarm with the app](/en/cuebly-app/send-help).
- **Set a timer alarm:** see [Timer alarm](/en/cuebly-app/timer-alarm).
- **Choose whether you receive messages:** the **Available** switch. See [Availability, presence and connection](/en/cuebly-app/availability-presence).
- **Read messages:** messages from the platform appear at once. Tap **OK** to confirm you read them.

![The Cuebly app after tapping a quick button tile. Marker 1 points at a Message dialog with the text sent by the scenario and an OK button, marker 2 at the confirmation Scenario started at the bottom.](/wiki-images/cuebly-app/cuebly-app-04-message.png)
*The app confirms that the scenario started (2). A text message from a scenario or from the platform shows as a dialog; tap OK to close it (1).*

## Is the app online?

The app tells the platform regularly that it is still running (a heartbeat). The platform uses this to show the app's connection: online, idle or offline. Phones decide themselves how often an app may run in the background, depending on battery, memory, charging and use, so the interval varies. [unverified: the 60 minute idle and 9 hour offline limits]

Messages and assistance requests reach apps that are online. That is why the onboarding asks to let the app run in the background.

## Languages

The app has the same 10 languages as the platform. Choose the language in **Settings**; it does not depend on the language of your phone. See [Supported languages](/en/about-cuebly/supported-languages).

---

## Draft notes (remove before publishing)

- **Views:** custom views only appear in the app on dev after a hidden feature switch (B14, B20). Publish the Views line only when that is solved in production; otherwise drop it.
- **Heartbeat numbers:** the previous page gave Android every 4 minutes, iOS at most every 15 minutes, idle after 60 minutes, offline after 9 hours. Not verified for the new app; left out.
- **OS minimums** (Android 10, iOS 14 on the previous page) not verified.
- **Assistance requests in the new app** are open work (development/frontend/mobile#66). Not mentioned until it ships.
- **Peripheral devices (e-B10):** not tested in the new app. The `cuebly-app/e-b10` page stays for the legacy app until tested.
- **White label:** the old "your own whitelabel" route is replaced by one app with branding (Jarno to confirm; see `cuebly-app/whitelabel` in the inventory).
- **Images:** Art's `cuebly-app/cuebly-app-02-home.png` and `-04-message.png`.
