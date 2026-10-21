---
path: customer-environment/devices/devcon-v4
title: Change device settings (DevCon V4)
description: Change the settings of a device over the air, sync them and undo changes
status: check
sources: frontend-design knowledge/modules/devices.md, glossary.md (DevCon V4), screenshots current/platform-v4/devices/ (Tess, V4 dev, 2026-10-20 and 2026-10-21)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Change device settings (DevCon V4)

With **DevCon** you change the settings of a device from the platform, over the air. You do not need the device in your hands or any technical tools. Cuebly V4 devices and Emerit devices use **DevCon V4**, described on this page. Other devices use the previous configurator, see [Devices](/en/customer-environment/devices).

## Open DevCon

1. Go to **Devices**.
2. Open the device card.
3. Click the gear icon **Change device configuration**.

DevCon opens on the right. The settings are grouped, for example **General**, **Wifi**, **Sound**, **Man down**, **Alarm numbers**, **Trusted numbers** and **Periodic positioning**. Which groups you see depends on the device type.

![DevCon V4 next to the device cards](image: devcon-v4-01-open)

## Change a setting

Change the setting you need. The platform stores the change right away, as the new setting for the device. Until the device has received it:

- the group shows an orange number, for example "1 setting not yet synced to the device",
- the save button at the top shows a badge: "Sync 1 change to the device".

Changes are stored on the platform at once, even before you sync. Keep this in mind when you work on a device that is in use.

## Send the changes to the device

1. Click the save button at the top of DevCon.
2. Check the list of settings to be saved and click **Save**.
3. Choose whether the device restarts now. Most settings only take effect after a restart.

![The Save configuration dialog with the settings to be saved](image: devcon-v4-02-sync)

If the device is offline, it receives the settings when it connects again. [unverified for DevCon V4]

## Undo changes that are not synced

Click **Discard changes** (the undo button at the top) to drop the changes that have not been sent to the device yet.

## More actions

The menu at the top of DevCon (three dots) has:

- **Restore device settings to defaults**
- **Reboot**

The history button shows earlier changes. [unverified: what the history shows]

## The Cuebly app in DevCon

For an app device (type Mobile App Lite), DevCon has the group **General** with:

- **Features**, such as **Voice connection on alarm**, **Teams** and **Timer alarm**. Each feature has two switches:
  - **Enabled**: whether the feature is on when the app starts.
  - **Change device configuration**: whether the app user may change the feature in the app's Settings.
- **Custom views**: pages of tiles for the app. Creating a view and choosing where custom views appear are stored on the platform at once; the app receives them with the next sync. See [Custom views](/en/customer-environment/devices/custom-views). [page not written yet]

The app's own Settings no longer has sound, inactivity or geofence settings. You set the app's features here, per device.

## Hide settings from the customer

Account managers can hide a group or a single setting of DevCon V4 from the customer's users, with the eye icons that appear when presentation mode is off. See [Presentation mode](/en/reseller-environment/presentation-mode).

---

## Draft notes (remove before publishing)

- **Answered (wiki report):** "Change device configuration" = may the app user change it in the app (`userConfigurable`); "Enabled" = the value the app starts with. Proposal 007 suggests one switch plus a lock; update if built.
- **Custom views:** answered in the wiki report: saving stores at once, the device gets it with the sync (v4-platform#443 point 10 covers the misleading help text). Custom views also only show in the app after a hidden feature switch on dev (B14, B20). The custom views page (N6) is held until that is resolved.
- **Offline devices:** from the V3 page; not verified for DevCon V4.
- **Save, open, download or upload a configuration, Run diagnostics:** V3 configurator features. Not seen in DevCon V4 by Tess; left out.
- **Which devices use DevCon V4:** code says V4 and Emerit devices; on V4 dev every device opens DevCon V4. Confirm for production.
- **Images:** requested from Art (devcon-v4-01, 02). Sources: `current/platform-v4/devices/02-devcon-v4-app-general.png`, `04-devcon-v4-sync.png`.
