---
path: cuebly-app/settings
title: App settings
description: What you find under Settings in the Cuebly app
replaces: cuebly-app/settings (2025-07-01)
status: check
sources: frontend-design knowledge/modules/mobile-app.md, screenshot current/app-v4/08-settings-nl.png (app 1.4.0, 2026-10-21)
last fact check: 2026-10-21
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

## Language

Choose the language of the app. The app has the same 10 languages as the platform. The language of the app does not depend on the language of your phone.

## Theme

Switch between **Light** and **Dark**.

## Logout

Logs you out of the app. You no longer receive messages or send alarms from this phone until you log in again.

At the bottom, **Version** shows the version of the app.

![Settings in the Cuebly app](image: app-settings-01)

## What changed from the previous app

- Settings is a tab in the bottom bar, not behind the menu icon.
- The sound settings, call permissions, inactivity (man down) alarm and the switch to enable the app in a geofence are not in the app's settings. [unverified: whether these are now set by the administrator in DevCon V4, or not available yet]

---

## Draft notes (remove before publishing)

- **Logout effect** ("no longer receive messages") is an assumption; verify with Tess.
- **Old settings:** the previous page described sound settings, call permissions, inactivity alarm and the geofence enable switch. None were seen in 1.4.0. Ask Tess or Jarno where they went before publishing the "What changed" section.
- **Tapping a Status line opens phone settings:** the screenshot shows arrows; behaviour not verified.
- **Dev menu** (long press on the Settings title in development builds) is left out on purpose.
- **Images:** requested from Art (app-settings-01). Source is Dutch (`current/app-v4/08-settings-nl.png`); an English capture is needed (T7). The screenshot shows a device id at the top; Art should crop or redact it.
