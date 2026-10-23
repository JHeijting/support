---
path: customer-environment/users
title: Users and permissions
description: Give people access to a customer environment and choose what they may do
replaces: customer-environment/users (2025-07-01)
status: check
sources: frontend-design knowledge/modules/account-management.md (permissions dialog), wiki-report.md (users row), screenshot current/platform-v4/users/01-permissions-dialog.png (Tess, V4 dev, 2026-10-20 and 2026-10-21), Tess T13 answers 2026-10-21 (tested: Add user)
last fact check: 2026-10-22
author: David van der Berg
---

# Users and permissions

Users are the people who log in to a customer environment. You choose per user what they may do, with **permissions**.

You find the users of an account under **Administration** > **Users** in the customer environment.

## Add a user

1. Go to **Users** and click **Add**. **New user** opens.
2. Fill in **First name**, **Last name** (optional) and **Email address**.
3. Leave **Inform user by email** ticked to send the user an email about the new account, or untick it.
4. Click **Save**. It stays disabled until the required fields are filled.

Then give the user permissions (below).

## Permissions

Open the menu at the end of a user's row (three dots) and choose **Permissions**. The dialog has two ways to give access:

- **Full access**: the user may do everything in this account.
- **Per subject**: for each subject (for example **Alarms**, **Contacts**, **Devices**, **Geofences**, **Scenarios** or **Users**), tick what the user may do:
  - **Read**: see it.
  - **Update**: change it.
  - **Manage**: create and delete it. [unverified: exact meaning of Manage versus Update]

Click **Save**.

![The permissions dialog of a user. Marker 1 points at Full access, marker 2 at the columns Read, Update and Manage, with one row per subject such as Alarms, Contacts, Devices, Geofences and Scenarios. Marker 3 points at Save.](/wiki-images/users/users-01-permissions-dialog.png)
*Give a user Full access (1), or choose per subject whether they may read, update or manage it (2). Then click Save (3).*

### Examples

| The user should | Give |
|---|---|
| Handle alarms only | Read and Update on **Alarms** and **Alerts**, Read on **Devices** [unverified: minimum set] |
| Manage the account like an administrator | **Full access** |

## Other actions on a user

The menu at the end of a user's row also has:

- **Reset password**: the user receives an email to set a new password.
- **Delete**: removes the user. Confirm to continue.

## App users

People who use the Cuebly app are users of the account too. Their app is added as a device of the type Mobile App Lite. See [Add an app user](/i/126).

---

## Draft notes (remove before publishing)

**Removed from the page (wiki rule: current product only, Jarno 2026-10-21). Kept here for the cutover plan:**

- The roles Administrator, Portal user, App user and Alarm receiving center are replaced by permissions per subject.
- App licenses are gone: the app is added as a device.

- **Customer environment Users page:** the permissions dialog and the user menu (Permissions, Reset password, Delete) were verified on the Account management panel and the V4 permissions screenshot. Add user: tested by Tess (T13, 23:20 CEST): First name, Last name (optional), Email address, "Inform user by email" (on by default), nothing else. What the email contains, and the permissions a new user starts with, are not tested; the text does not say.
- **Subjects:** 25 in total; the screenshot shows Translations, Alarms, Contacts, Accounts, Communications, Device_configs, Dashboards, Geofences, Sites, Alarm Protocols, Scenarios, Users, Arc, Whitelabels, Alerts, App, Api_tokens, Permissions and more. Several are raw names ("Device_configs", "Api_tokens") and some are not meaningful inside a customer account (Accounts, Whitelabels, Translations). Worth a ticket for readable names; the article names only the clear ones.
- **"Other permissions"** with raw strings such as `read.accounts.<id>` is left out on purpose.
- **Read, Update, Manage:** meaning assumed from the names. The examples table needs Jarno or Tess to confirm a minimum set for an operator.
- **Two-factor authentication, welcome emails, bulk actions:** on the V3 page, not verified in V4 (wiki report: "2FA: check"). Left out.
- **Proposal 006** suggests standard roles plus a custom role; update if built.
- **Images:** Art's `users/users-01-permissions-dialog.png`.
