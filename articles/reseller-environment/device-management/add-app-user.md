---
path: reseller-environment/device-management/add-app-user
title: Add an app user
description: Give a user the Cuebly app by adding a Mobile App Lite device
status: check
sources: frontend-design knowledge/modules/devices.md, mobile-app.md, glossary.md (Tess, V4 dev and app 1.4.0, 2026-10-20 and 2026-10-21)
last fact check: 2026-10-21
author: David van der Berg
---

# Add an app user

In Cuebly V4 the app is a device like any other. To give someone the Cuebly app, you add a device of the type **Mobile App Lite** to the customer's account and link it to a user of that account. You can create the user in the same step.

You need no app licenses for this.

## Before you start

- The customer account exists. See [Account management](/en/reseller-environment/account-management).
- You add devices in your own environment, under **Devices**. You cannot add a device from inside a customer environment.

## Add the app device

1. Go to **Devices** and click **Add**.
2. Choose the device type **Mobile App Lite**.
3. Choose the **account** of the customer.
4. Link a user:
   - **Create a new user**: fill in the first name, last name (optional) and email address. Leave **Inform user by email** on, so the user receives the login details by email.
   - **Select an existing user** of that account.
5. Fill in a **device name**, for example the user's name. The name is used in alarms and in scenario messages.
6. Click **Save**. The message "Device has been saved" appears.

![The New device form for the Cuebly app with create new user chosen. Marker 1 points at the create new user option, marker 2 at First name, marker 3 at Email address, marker 4 at the ticked Inform user by email box, marker 5 at Device name. Last name is optional.](/wiki-images/add-an-app-user/add-an-app-user-03-new-user.png)
*For someone without a login, choose create new user (1). Fill in the first name (2) and email address (3). Keep Inform user by email ticked (4) so the user gets their login details. Give the device a name (5) and click Save.*

## What the user does next

1. Install the Cuebly app from the App Store or Google Play. [unverified: store names and links]
2. Log in with the email address and the password from the welcome email.
3. Follow the onboarding. The app asks, one step at a time, for:
   - **Location**, set to "Allow all the time", so the app can send a location with an alarm and check locations (geofences),
   - **Notifications**, to receive messages,
   - **Critical alerts** (Android), so alarms and messages sound through Do Not Disturb,
   - **Microphone**,
   - **Background activity**, so the phone does not stop the app.
4. At the end, the app shows a summary of what is enabled.

After login the app shows the branding of the customer's account.

![The last onboarding screen of the Cuebly app, titled Welcome: You're all set. Marker 1 points at the list Location, Notifications, Critical alerts, Microphone and Allow app, each marked Enabled.](/wiki-images/cuebly-app/cuebly-app-01-onboarding-complete.png)
*At the end of the onboarding the app shows which permissions are on (1). You can change them later in the phone settings.*

## Where the app user shows up

- In the customer environment, the app is one of the **Devices**, with its own device card.
- You can add the device to **teams**, use it in **scenarios** and change its settings with **Change device configuration** (DevCon V4).
- In **Devices** in your own environment, a Mobile App Lite device has the actions **Edit**, **Manage alarm center**, **Login as** and **Delete**.

## Good to know

- An app user is a user of the customer account. The device links that user to the app.
- A Mobile App Lite device cannot be imported from a file. Add app users one at a time.
- If the user forgets the password, they tap **Forgot password** on the login screen of the app.

---

## Draft notes (remove before publishing)

- **Select an existing user does not work well on dev** (Jarno, to investigate); creating a new user in the same form does. Keep the option in the text only once it works, or add a note.
- **Device types:** on dev only "Mobile App Lite" is offered for Tess's login. Mobile App Pro and Pro Voice are not mentioned until confirmed.
- **Store names and links, OS minimums:** not verified for the new app. The old page says Android 10 and iOS 14.
- **Login errors:** every login error shows "Credentials invalid", also network errors (app code). Consider a troubleshooting line once the app distinguishes them.
- **Onboarding bug:** after returning from system settings in the location step, the notifications step may not react until the app is restarted (1.4.0). Leave out of the article; add to the app FAQ if it ships like this.
- **Branding:** "shows the branding of the customer's account" is from the fact sheet, not tested with a partner brand.
- **Images:** requested from Art (add-app-user-01, 02).
