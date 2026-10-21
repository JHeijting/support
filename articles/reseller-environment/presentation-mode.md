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

![The bottom of the left menu in a customer account. Marker 1 points at the presentation mode icon next to the language selector. The icon is green: presentation mode is on.](/wiki-images/presentation-mode/presentation-mode-01-icon-on.png)
*The presentation mode icon sits at the bottom of the menu, next to the language (1). Green means on: you see the account as the customer's users see it.*

![The bottom of the left menu with the presentation mode icon grey, which means off. A tooltip reads: Toggle presentation mode for customers on/off.](/wiki-images/presentation-mode/presentation-mode-02-icon-off.png)
*Click the icon to switch presentation mode off (1). Grey means off. After every page load or new login it is on again.*

**Presentation mode is on when you start.** Every time you open or reload a page, or log in again, it is switched on. Switch it off again when you need it.

Only account managers who manage the account see the icon. The customer's own users never do.

## Choose which device settings the customer sees

In **DevCon V4** you can hide a group of settings, or a single setting, from the customer's users.

1. Switch presentation mode **off** (grey icon).
2. Go to **Devices**, open a device card and click the gear icon **Change device configuration**.
3. Every group (for example **General**) and every setting has an eye icon on the right.
4. Click the eye of the group or setting you want to hide.

![The device configurator of an app device with presentation mode off. Marker 1 points at the grey presentation mode icon. Marker 2 points at the eye icon of the group General, marker 3 at the eye icon of one setting. Every group and setting has an eye icon.](/wiki-images/presentation-mode/presentation-mode-03-devcon-off-eye-icons.png)
*With presentation mode off (1), every group (2) and every setting (3) in the device configurator has an eye icon. Click an eye to hide that group or setting from the customer's users.*

What you hid stays visible to you, greyed out, with a red crossed eye. Hover over it to see "Account user can't see this section". Click the eye again to show it to the customer again.

![The device configurator with presentation mode off and items hidden. Marker 1 points at a red crossed eye on the group General, with the tooltip: Account user can't see this section. Marker 2 points at the Timer alarm setting, greyed out because it is hidden.](/wiki-images/presentation-mode/presentation-mode-04-hidden-greyed-out.png)
*A hidden group or setting shows a red crossed eye (1) and stays visible to you, greyed out (2). The change is saved at once, for every device of this type in the account.*

Switch presentation mode **on** to check the result: the eye icons are gone and the hidden items are not shown, exactly as the customer sees it.

![The device configurator of an app device with presentation mode on. Marker 1 points at the green presentation mode icon. Marker 2 points at the group General, which has no eye icon. Hidden items are not shown at all.](/wiki-images/presentation-mode/presentation-mode-05-devcon-customer-view.png)
*With presentation mode on (1) there are no eye icons (2) and hidden items are left out: this is what the customer's users see.*

### Good to know

- **Saved at once, for the whole account.** A click on an eye is saved immediately. You do not need the DevCon save button. The choice applies to every device of that type in the account, not only to the device you have open.
- **Hiding is not switching off.** Hiding a setting does not change the setting on the device. To switch a feature off, change the setting itself (for example **Enabled**), and then hide it if the customer should not change it back.
- **Change first, then hide.** A change in DevCon V4 is stored right away. If you change a setting and then hide it, your change stays.

## Other things presentation mode hides

With presentation mode on, the platform also hides some other details, for example the device id next to the device name in alarm details, and the instructions field on alarm protocol cards. [unverified in V4: taken from the platform code]

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
- **Removed from the text after Manon's review (no workarounds for gaps, no invented intent):**
  - Every group hidden gives the customer an empty panel without explanation: ticket draft **B67**. Describe the intended behaviour once Jarno answers Q10.
  - With Timer alarm hidden, the app still shows Set timer alarm (screenshot 07): hiding works on the web only. Whether the app should follow is open (Q10 area); Art's images 06 and 07 are not used for now.
  - Why the switch turns on after every page load is not documented; ticket draft **F31** asks to remember the choice. The text only says what happens.
  - Hiding scenarios: ticket draft **F30**. The text states the fact that V4 cannot hide scenarios.
- **Open questions for Jarno** (from Tess): should V4 hide scenarios again; should the choice be remembered after reload; what should a customer see when every group is hidden. Update the article when answered.
- **Other hidden details:** device id and protocol instructions come from code; alarm protocols have no menu in V4 customer environments (wiki report). Verify or drop that section.
- **Images:** Art's set `wiki-images/presentation-mode/` (frontend-design main), from Tess's screenshots. Paths in the article are relative to `wiki-images/`; adjust to the wiki's upload folder when publishing.
