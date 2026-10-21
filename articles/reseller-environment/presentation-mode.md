---
path: reseller-environment/presentation-mode
title: Presentation mode
description: See a customer account the way the customer sees it, and choose which device settings the customer may see
status: review
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

**Presentation mode is always on when you log in to a customer account.** It is also switched on again when you reload a page. Switch it off when you need it.

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

## Scenarios

In V4, scenarios cannot be hidden from the customer yet. All scenarios are shown, with presentation mode on and off.

## What changed from V3

- The icon and its place are the same as in V3.
- New in V4: the eye icons in DevCon V4, to hide groups and settings from the customer.
- In V3 you could hide a scenario from the customer, for example the scenario that sends alarms to an alarm receiving centre. In V4 that is not possible yet.

---

## Draft notes (remove before publishing)

**Decided by Jarno (Q10, 2026-10-21), waiting to be built:**

1. **Hide scenarios:** scenarios must be hideable from the customer again (ticket draft **F30**). When built, replace the Scenarios section with how to hide one, and remove "yet" in the two places it appears.
2. **Every group hidden:** the panel must then tell the customer's user that they have no permission to change anything (ticket draft **B67**; today the panel is empty). When fixed, add one line under "Good to know": "If you hide every group of a device, the customer's users see that they have no permission to change its settings."
3. **Always on when you log in to an account:** intended (F31 "remember the choice" is not wanted). The article describes it as intended.

**Still open:** hiding works in DevCon on the web only; the app still shows a hidden feature (for example Set timer alarm). Intended, or should the app follow? Left out of the article. Not in Q10; ask Jarno if it matters for the article.

**One check for Tess before publishing:** the customer's own view was checked with presentation mode on, not yet with a customer user's login.

Verified by Tess (V4 dev and the web frontend code, 2026-10-21): the icon, its tooltip and colours, on after every login and page load, the eye icons, the red crossed eye and its tooltip, saving at once for the whole account and every device of that type, hiding does not change the device setting, scenarios cannot be hidden, presentation pages are a different feature. Left out: other details hidden by presentation mode (from code only). Images: Art's `presentation-mode` set 01 to 05, from Tess's screenshots; image 06 (empty panel) is not used, it shows the bug B67.
