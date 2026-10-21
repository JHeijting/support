---
path: cuebly-app/onboarding
title: Onboarding
description: The first steps after logging in to the Cuebly app, and why each permission is needed
replaces: cuebly-app/onboarding (2025-07-01)
status: check
sources: frontend-design knowledge/modules/mobile-app.md, fact sheet 2026-10-21, screenshots current/app-v4/02 and 03 (app 1.4.0, Android emulator); the "why" texts are kept from the previous wiki page
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Onboarding

The first time you log in, the Cuebly app walks you through a few steps. Each step asks for one permission and explains why. Please give all of them: the app is a safety tool, and your phone must not stop it or silence it when it matters.

## Why the app needs these permissions

Android and iOS stop or limit apps to save battery and memory, for example when the phone is low on memory, when an app is not opened often, or at times you normally do not use your phone. For most apps that is fine. For a safety app it means an alarm or a message could arrive late, or not at all.

## The steps

Tap **Continue** to go to the next step. The dots at the bottom show where you are.

1. **Welcome**
2. **Location**: the app sends your location with an alarm. It also checks on the phone whether you are inside the locations (geofences) your organisation assigned to you, and reports only whether you are present. Choose **Allow all the time** in the phone settings, so this also works when the app is in the background. [wording to confirm with Jarno]
3. **Notifications**: to receive messages from the platform. You can tap **Skip for now** and allow it later.
4. **Critical alerts** (Android): so alarms and messages sound even when the phone is on Do Not Disturb. The app asks for notifications, Do Not Disturb access, display over other apps, and sound and vibration for its alerts.
5. **Microphone**: after an SOS alarm, the app can open a voice connection with the person handling the alarm. The microphone is also used for push to talk.
6. **Background activity**: tap **Allow app**, so the phone does not stop the app in the background.
7. **Done**: a summary shows what is enabled.

If a permission is already given, the step shows a check mark.

![The Location step of the Cuebly app onboarding. Marker 1 points at the title Location and the text: your location will only be sent when you make an alarm. Marker 2 points at the Continue button.](/wiki-images/cuebly-app/cuebly-app-06-onboarding-location.png)
*The app explains why it needs your location (1). Tap Continue (2) and allow location access all the time in the phone settings.*

![The last onboarding screen of the Cuebly app, titled Welcome: You're all set. Marker 1 points at the list Location, Notifications, Critical alerts, Microphone and Allow app, each marked Enabled.](/wiki-images/cuebly-app/cuebly-app-01-onboarding-complete.png)
*At the end of the onboarding the app shows which permissions are on (1). You can change them later in the phone settings.*

## Change a permission later

Open **Settings** in the app. Under **Status** you see whether notifications, critical alerts and location are allowed. Tap a line to fix it. See [App settings](/en/cuebly-app/settings).

---

## Draft notes (remove before publishing)

- **Location wording (wiki report):** both happen: the app checks assigned geofences on the phone and reports presence; the location itself goes with an alarm. The article now says so; Jarno to confirm the wording, and the app's own text ("only sent when you make an alarm") may need the same fix.
- **iOS:** all steps were checked on Android only. iOS steps (critical alerts on iOS, location wording) are not verified. The previous page had iOS-only Bluetooth and Critical alerts steps.
- **Microphone (answered, wiki report):** voice connection after an SOS, and push to talk.
- **Steps never skip** when a permission is already given (they show a check mark but stay, "Permission needed"); Jarno wants detect and skip. Update when changed.
- **Known bug:** after returning from system settings in the location step, the notifications step may not react until the app is restarted. If it ships, add a tip: "If Continue does not react, close and open the app."
- **Security code and phone number steps** from the previous app were not seen in 1.4.0; left out.
- **Images:** requested from Art (onboarding-01, 02). Sources: `current/app-v4/02-onboarding-location-en.png`, `03-onboarding-complete-en.png` (Art's `cuebly-app` set has the summary).
