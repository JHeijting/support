---
path: reseller-environment/presentation-mode
title: Presentation mode
description: See a customer account the way the customer sees it, and choose which device settings the customer may see
status: check
sources: frontend-design knowledge/modules/presentation-mode.md and its wiki notes, screenshots current/platform-v4/presentation-mode/ (Tess, V4 dev and frontend code, 2026-10-21)
last fact check: 2026-10-21
author: David van der Berg
---

# Presentation mode

When you work inside a customer account as an account manager, **presentation mode** shows you the account exactly as the customer's own users see it. Switch it off to see everything, including what is hidden from the customer, and to choose which device settings the customer may see.

Presentation mode is not the same as a presentation page. A presentation page is a slideshow of dashboards for a wall screen; see [Dashboards](/en/customer-environment/dashboards).

## Switch presentation mode on or off

1. Log in to the customer environment. See [Account management](/en/reseller-environment/account-management).
2. Find the presentation mode icon at the bottom of the menu, next to the language selector. Its tooltip reads "Toggle presentation mode for customers on/off".
3. Click the icon.
   - **Green**: presentation mode is **on**. You see what the customer sees.
   - **Grey**: presentation mode is **off**. You see everything.

![The presentation mode icon, on (green) and off (grey)](image: presentation-mode-01-icon)

**Presentation mode is always on when you start.** Every time you open or reload a page, or log in again, it is switched on. This is on purpose: you never show a customer something by accident. Switch it off again when you need it.

Only account managers who manage the account see the icon. The customer's own users never do.

## Choose which device settings the customer sees

In **DevCon V4** you can hide a group of settings, or a single setting, from the customer's users. Use it to keep the device settings simple for a customer, or to protect settings the customer should not change.

1. Switch presentation mode **off** (grey icon).
2. Go to **Devices**, open a device card and click the gear icon **Change device configuration**.
3. Every group (for example **General**) and every setting has an eye icon on the right.
4. Click the eye of the group or setting you want to hide.

![DevCon V4 with presentation mode off: an eye icon on every group and setting](image: presentation-mode-02-eye-icons)

What you hid stays visible to you, greyed out, with a red crossed eye. Hover over it to see "Account user can't see this section". Click the eye again to show it to the customer again.

![A hidden group and a hidden setting, greyed out with a red crossed eye](image: presentation-mode-03-hidden-greyed)

Switch presentation mode **on** to check the result: the eye icons are gone and the hidden items are not shown, exactly as the customer sees it.

![DevCon V4 as the customer sees it](image: presentation-mode-04-customer-view)

### Good to know

- **Saved at once, for the whole account.** A click on an eye is saved immediately. You do not need the DevCon save button. The choice applies to every device of that type in the account, not only to the device you have open.
- **Hiding is not switching off.** Hiding a setting only changes what the customer's users see in DevCon on the web. It does not change the setting on the device, and it does not change the app. For example: with **Timer alarm** hidden, the app user still sees **Set timer alarm** in the app. To switch a feature off, change the setting itself (for example **Enabled**), and then hide it if the customer should not change it back.
- **Change first, then hide.** A change in DevCon V4 is stored right away. If you change a setting and then hide it, your change stays.
- **Do not hide every group.** If you hide all groups of a device, the customer sees an empty settings panel with only the device name.

## Other things presentation mode hides

With presentation mode on, the platform also hides some details that are meant for account managers only, for example the device id next to the device name in alarm details, and the instructions field on alarm protocol cards. [unverified in V4: taken from the platform code]

## Scenarios

In V4, scenarios cannot be hidden from the customer. All scenarios are shown, with presentation mode on and off.

## What changed from V3

- The icon and its place are the same as in V3.
- New in V4: the eye icons in DevCon V4, to hide groups and settings from the customer.
- In V3 you could hide a scenario from the customer, for example the scenario that sends alarms to an alarm receiving centre. In V4 that is not possible.

---

## Draft notes (remove before publishing)

- **Customer user's view not tested live** (no web login for a customer user yet). From the code, hidden items are always enforced for users who cannot present as customer. Verify with a customer login before publishing.
- **"Every device of that type"**: the module says the policy is per account and "applies to every device of that type in the account". Confirm whether hiding a General setting on a Mobile App Lite also hides a General group on an EV04 (same group key), or only on the same type.
- **Two managers at once:** each eye click writes the whole account setting; not tested whether one overwrites the other. Leave out unless it proves to be a problem.
- **Who sees the icon:** account managers who manage the account, and V3 shadow users (`canPresentAsCustomer`). "V3 shadow user" is left out of the customer text.
- **Open questions for Jarno** (from Tess): should V4 hide scenarios again; should the choice be remembered after reload; what should a customer see when every group is hidden. Update the article when answered.
- **Other hidden details:** device id and protocol instructions come from code; alarm protocols have no menu in V4 customer environments (wiki report). Verify or drop that section.
- **Images:** requested from Art (presentation-mode-01 to 04). Sources: `current/platform-v4/presentation-mode/01` and `02` (icon), `04` (eye icons), `05` (hidden greyed), `03` (customer view). Optional fifth image from `06` (empty panel) if Jarno wants the warning illustrated.
