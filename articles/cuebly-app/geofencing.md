---
path: cuebly-app/geofencing
title: App geofencing
description: How the Cuebly app knows whether you are inside a location
replaces: cuebly-app/geofencing (2025-07-01)
status: check
sources: frontend-design knowledge/modules/mobile-app.md (night test 2026-10-21), 2026-10-21-wiki-gaps.md, wiki-report.md, glossary.md (Presence)
last fact check: 2026-10-21
author: David van der Berg
---

# App geofencing

A geofence is a zone on the map, for example a building or a site. The Cuebly app can tell the platform whether you are inside the geofences assigned to you. The platform uses this to show who is present, and to start scenarios when someone enters or leaves.

## How it works

- Your administrator creates geofences in the customer environment and links devices or teams to them. See [Geofences](/en/customer-environment/geofences).
- The app checks on the phone whether you are inside those geofences, also when the app is in the background.
- The app reports when you enter or leave. The platform shows you as present in the geofence, and can start a scenario with the trigger **Enter geofence** or **Exit geofence**.

On Android you see a permanent notification "Cue is checking configured geofences" while the app does this.

## See your locations in the app

Go to **Groups** > **Locations**. You see the geofences assigned to you, with their size, a map and who is present.

## What you need

- Location permission set to **Allow all the time**. See [Onboarding](/en/cuebly-app/onboarding).
- Background activity allowed for the app.

## What changed from the previous app

- You no longer set up geofencing in the device configurator under "App settings". Your administrator links geofences to devices and teams on the platform.
- There is no button to set your presence by hand.
- The setting that switched the app on or off when entering or leaving a geofence is not in the new app. [unverified: see draft notes]

---

## Draft notes (remove before publishing)

- **Presence label in the app:** Groups > Locations counts presence as "Available / Unavailable" today (B17, proposal 004). The article says "who is present". Check the label before publishing.
- **How often the app checks** (Android every 15 minutes, iOS when the system allows, on the previous page): not verified for the new app; left out.
- **Battery use** remark from the previous page: left out until verified.
- **Auto enable or disable in a geofence:** not seen in DevCon V4 for Mobile App Lite (wiki gaps). Ask Jarno whether it comes back.
- **iOS:** only Android was tested.
- **Images:** app geofencing waits for T7 (invented location). Art left out the existing geofence detail screenshot because it shows a real town.
