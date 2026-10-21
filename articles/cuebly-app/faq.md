---
path: cuebly-app/faq
title: FAQ - mobile app
description: Frequently asked questions about the Cuebly app
replaces: cuebly-app/faq (2025-07-01)
status: check
sources: previous wiki page; frontend-design knowledge/modules/mobile-app.md, wiki-report.md (faq row)
last fact check: 2026-10-21
author: David van der Berg
---

# FAQ - mobile app

## Why is there a permanent notification on my Android phone?

The app must keep running in the background, so it can send an alarm and check your locations (geofences). Android only allows that when the app shows a permanent notification. In the new app it reads "Cue is checking configured geofences".

You can hide the notification and keep the function: in the Android settings for the app, switch off the notification channel of that notification. [unverified: channel name in the new app]

## Why does the app ask for so many permissions?

Phones stop or limit apps to save battery. For a safety app that could mean an alarm or message arrives late. See [Onboarding](/en/cuebly-app/onboarding) for each permission and why it is needed.

## Why does an alarm or message sound when my phone is on Do Not Disturb?

On Android the app asks for **Critical alerts**: permission to sound through Do Not Disturb. This is on purpose, so you do not miss an alarm or an urgent message. You can check the permission in the app under **Settings** > **Status**.

## My phone keeps stopping the app

Some phones stop apps in the background to save battery. Check that:

- **Background activity** is allowed for the app (the onboarding asks for it),
- battery optimisation is switched off for the app in the phone's settings. [unverified: exact steps differ per phone]

## I cannot log in

Check your email address and password. Tap **Forgot password** on the login screen to get a new one by email. If it still fails, check your internet connection: the app shows the same message for a wrong password and for no connection. [see draft notes]

---

## Draft notes (remove before publishing)

- **Login message:** every login error shows "Credentials invalid", also network errors (app code). If the app gets separate messages, update the answer.
- **Notification channel** name for hiding the permanent notification: the old app used "App status notification". Check in the new app.
- **Critical alerts and battery optimisation** were suggested by Tess (wiki report). Battery steps not verified per phone brand.
- **iOS:** answers are Android based.
