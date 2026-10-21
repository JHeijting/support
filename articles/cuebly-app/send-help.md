---
path: cuebly-app/send-help
title: Send an alarm with the app
description: Ask for help with the Send help! button or the side button of a Samsung XCover phone
status: check
sources: frontend-design fact sheet 2026-10-21, knowledge/modules/mobile-app.md (SOS, night test 2026-10-21), qa/to-test/mobile-23-xcover-button/report.md (XCover side button, development build of app 1.4.0, 2026-10-21), wiki-report.md
last fact check: 2026-10-21
author: David van der Berg
---

# Send an alarm with the app

When you need help, the Cuebly app sends an alarm to the platform, with your location. The person who handles alarms for your organisation sees it at once.

## With the Send help! button

1. Open the app. **Send help!** is the large red button on **Home**.
2. **Press and hold** the button for **3 seconds**.

A short tap does nothing. This prevents alarms from a phone in your pocket.

The app confirms with "Alarm is sent". The alarm arrives on the platform within a few seconds, as an **SOS button** alarm with your device name, the time and your location.

![The home screen of the Cuebly app. Marker 1 points at the large red Send help! button, marker 2 at the Status card with the Available switch, marker 3 at a running SOS Timer banner with 23:54 left and a Cancel button, marker 4 at the bottom bar with Home, Groups, Views and Settings.](/wiki-images/cuebly-app/cuebly-app-02-home.png)
*Hold Send help! for 3 seconds to send an alarm (1). Switch your availability under Status (2). A running timer alarm shows at the top, with Cancel (3). The bottom bar (4) leads to Groups, Views and Settings.*

## With the side button of a Samsung XCover

On a Samsung Galaxy XCover phone you can use the programmable side button, also when the app is in the background. [see draft notes]

1. **Press and hold** the side button.
2. The phone vibrates when you press, then gives four short pulses as a warning.
3. Keep holding: after **3 seconds** the phone vibrates long, and the alarm is sent.

Let go before the long vibration to cancel.

## What happens next

- The alarm appears in **Alerts** in the customer environment and can start scenarios, for example a message to colleagues nearby.
- The app may open a voice connection, so the person who handles the alarm can hear you. This is set per device by your administrator (**Voice connection on alarm** in DevCon V4).
- The app does not show yet when your alarm is picked up or closed. [see draft notes]

## Tips

- Give the app permission to use your location **all the time**. With a location fix, the alarm arrives faster and with your position.
- Test the alarm together with your administrator, so they know it is a test.

---

## Draft notes (remove before publishing)

- **XCover side button** was tested on a development build of app 1.4.0 with a simulated button (development/frontend/mobile#23 passed; vibration timing on mobile#48). Publish this section only when the release that contains it is in the stores, and check whether the button must be set up first (Samsung settings or the app's "SOS shortcuts" in Settings; wiki report mentions SOS shortcuts). Phone model names: check which XCover models.
- **Without a location fix** the alarm currently waits up to 30 seconds before it is sent (B13). The "within a few seconds" claim holds with a location fix only; keep the tip, and update once B13 is fixed.
- **No feedback after sending** (F8): the app only says "Alarm is sent". Update if the app gets follow-up feedback.
- **Short tap gives no hint** (F7). If the app adds a hint, mention it.
- **Voice connection:** wiki report and the XCover report (RTC started). Whether it opens for every alarm depends on the DevCon V4 setting; verify the wording with Tess.
- **Images:** Art's `cuebly-app/cuebly-app-02-home.png`. No image of the XCover button (physical button; a photo or none).
