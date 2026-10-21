---
path: customer-environment/devices/devcon-v4
title: Change device settings (DevCon V4)
description: Change the settings of a device over the air, sync them and undo changes
status: review
sources: frontend-design knowledge/modules/devices.md, glossary.md (DevCon V4), screenshots current/platform-v4/devices/ (Tess, V4 dev, 2026-10-20 and 2026-10-21)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Change device settings (DevCon V4)

With **DevCon** you change the settings of a device from the platform, over the air. You do not need the device in your hands or any technical tools. Cuebly V4 devices and Emerit devices use **DevCon V4**, described on this page. [Jarno: confirm for production] Other devices use the previous configurator, see [Devices](/en/customer-environment/devices).

## Open DevCon

1. Go to **Devices**.
2. Open the device card.
3. Click the gear icon **Change device configuration**.

DevCon opens on the right. The settings are grouped, for example **General**, **Wifi**, **Sound**, **Man down**, **Alarm numbers**, **Trusted numbers** and **Periodic positioning**. Which groups you see depends on the device type.

![The Devices page with the card of the Cuebly app open and the device configurator on the right. Marker 1 points at the gear icon on the card, marker 2 at the header of the device configurator with the device name and the save, history and menu icons.](/wiki-images/app-custom-views/app-custom-views-04-devcon-open.png)
*Click the gear icon on a device card (1). The device configurator opens on the right (2).*

## Change a setting

Change the setting you need. The platform stores the change right away, even before you send it to the device. Until the device has received it:

- the group shows an orange number, for example "1 setting not yet synced to the device",
- the save button at the top shows a badge: "Sync 1 change to the device".

## Send the changes to the device

1. Click the save button at the top of DevCon.
2. Check the list of settings to be saved and click **Save**.
3. Choose whether the device restarts now.

![The Save configuration dialog over the app settings, listing Custom views going to 1 items. Marker 1 points at the save icon with a badge for one change, marker 2 at the orange count next to the group General, marker 3 at the Save button in the dialog.](/wiki-images/app-custom-views/app-custom-views-03-sync-changes.png)
*A badge on the save icon (1) and an orange count on the group (2) show changes that the app does not have yet. Click the save icon, check the list and click Save (3). The undo arrow next to the save icon discards the changes.*

## Undo changes that are not synced

Click **Discard changes** (the undo button at the top) to drop the changes that have not been sent to the device yet.

## More actions

The menu at the top of DevCon (three dots) has:

- **Restore device settings to defaults**
- **Reboot**

## The Cuebly app in DevCon

For an app device (type Mobile App Lite), DevCon has the group **General** with:

- **Features**, such as **Voice connection on alarm**, **Teams** and **Timer alarm**. Each feature has two switches:
  - **Enabled**: whether the feature is on when the app starts.
  - **Change device configuration**: whether the app user may change the feature in the app's Settings.

The app's own Settings no longer has sound, inactivity or geofence settings. You set the app's features here, per device.

## Hide settings from the customer

Account managers can hide a group or a single setting of DevCon V4 from the customer's users, with the eye icons that appear when presentation mode is off. See [Presentation mode](/en/reseller-environment/presentation-mode).

---

## Draft notes (remove before publishing)

**For Jarno to decide:**

1. **Which devices use DevCon V4 in production:** the code says V4 and Emerit devices; on V4 dev every device opens DevCon V4.
2. **Custom views:** DevCon V4 shows them for app devices, but on dev they only reach the app after a hidden feature switch (B14, B20). The article leaves them out until they work in production. Add a section then (page N6)?
3. **Diagram (optional, Q11):** Art's `diagrams/diagrams-05-devcon-sync.png` (change, stored, not yet synced, save, synced) fits under "Change a setting". Only if Jarno allows concept diagrams.

Verified by Tess (V4 dev, 2026-10-20 and 2026-10-21): opening DevCon, the groups, storing at once with the orange count and the sync badge, the Save configuration dialog and the restart question, Discard changes, the menu, the two switches per app feature (wiki report), hiding with presentation mode. Left out because not verified in V4: offline devices, history, saving and loading configurations, diagnostics. Images: Art's `app-custom-views` set, from Tess's screenshots.
