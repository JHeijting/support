---
path: cuebly-app/settings
title: App settings
description: What you find under Settings in the Cuebly app
replaces: cuebly-app/settings (2025-07-01)
status: check
sources: frontend-design knowledge/modules/mobile-app.md, screenshot current/app-v4/08-settings-nl.png (app 1.4.0, 2026-10-21)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# App settings

Tap **Settings** in the bottom bar of the Cuebly app. From top to bottom you find:

## Your account

Your name, your email address and the device number of this app. Support may ask for the device number.

## Availability

The **Available** switch. When it is on, you receive messages and assistance requests. You find the same switch on the **Home** screen. See [Availability, presence and connection](/en/cuebly-app/availability-presence).

## Status

Shows whether the app has the permissions it needs:

- **Notifications**
- **Critical alerts**
- **Location**

A green check mark means the permission is given. Tap a line to open the phone settings and fix it.

## Timer

**Set timer alarm** starts a timer that raises an alarm if you do not cancel it in time. See [Timer alarm](/en/cuebly-app/timer-alarm).

## SOS shortcuts

Ways to send an alarm without opening the app, for example the side button of a Samsung XCover phone. [unverified: exact options; see draft notes]

## Language

Choose the language of the app. The app has the same 10 languages as the platform. The language of the app does not depend on the language of your phone.

## Theme

Switch between **Light** and **Dark**.

## Logout

Logs you out of the app. [unverified: after logout the phone no longer receives messages or sends alarms]

At the bottom, **Version** shows the version of the app.

![The Settings screen of the Cuebly app: the user's name, Availability with the Available switch, Status of Notifications, Critical alerts and Location, Timer with Set timer alarm, Shortcuts with SOS shortcuts, and Language. The email address and device number are hidden.](/wiki-images/cuebly-app/cuebly-app-07-settings.png)
*Settings in the Cuebly app.*

## What changed from the previous app

- Settings is a tab in the bottom bar, not behind the menu icon.
- The sound settings, call permissions, inactivity (man down) alarm and the switch to enable the app in a geofence are no longer in the app's settings. Your administrator sets the app's features per device in DevCon V4, for example **Voice connection on alarm**, **Teams** and **Timer alarm**, and decides whether you may change them yourself. See [Change device settings (DevCon V4)](/en/customer-environment/devices/devcon-v4).

---

## Draft notes (remove before publishing)

- **Logout effect** ("no longer receive messages") is an assumption; verify with Tess.
- **Answered (wiki report):** old settings are not in the new app; features are set per device in DevCon V4. Whether inactivity (man down) and sound settings exist at all in the new app is not confirmed; the text does not promise them.
- **SOS shortcuts:** the wiki report lists an "SOS shortcuts" section in Settings and the Samsung XCover side button (works in the background; press, warning and commit vibrations). Not in Tess's 1.4.0 screenshot. Get the exact options from Tess before publishing, or write a separate page (inventory N12).
- **Tapping a Status line opens phone settings:** the screenshot shows arrows; behaviour not verified.
- **Dev menu** (long press on the Settings title in development builds) is left out on purpose.
- **Images:** requested from Art (app-settings-01). Source is Dutch (`current/app-v4/08-settings-nl.png`); an English capture is needed (T7). The screenshot shows a device id at the top; Art should crop or redact it.
