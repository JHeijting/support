---
path: reseller-environment/account-management
title: Account management
description: Create and manage customer accounts and sub-account managers in Cuebly V4
replaces: reseller-environment/account-management (2025-07-01)
status: check
sources: frontend-design knowledge/modules/account-management.md, knowledge/v4-gaps.md, glossary.md (Tess, V4 dev, 2026-10-20 and 2026-10-21)
last fact check: 2026-10-21
author: David van der Berg
---

# Account management

Each customer gets its own **account**: an isolated customer environment with its own devices, users, scenarios and settings. As an account manager you create these accounts, manage their settings and log in to them to set them up or give support.

You find account management in two places in the menu:

- **Accounts**: a table of all your accounts.
- **Account management**: a tree of your own organisation, with your accounts, your sub-account managers and your users.

What you see in the menu depends on your permissions.

![The Accounts table with the toolbar and the row actions](image: account-management-01-accounts)

## Accounts or sub-account managers

When you create a new account, you choose what it is:

- **Account**: a customer environment for one customer.
- **Sub-account manager**: an account manager below you, for example a dealer or a branch office. A sub-account manager can create and manage its own accounts, users and devices. Everything beneath a sub-account manager counts towards your own account manager.

## Create an account

1. Go to **Accounts** and click **Add**.
2. Choose **Account** or **Sub-account manager**.
3. Optional: fill in your **own reference**. Use it for your own administration; it is shown in reports and downloads.
4. Fill in the **account name** and choose the **language** of the customer environment.
5. Under **Users**, tick the users of your organisation who may manage this account. All users are ticked by default. Users who are not ticked cannot see or manage the account.
6. Optional: set the **end of trial period**.
7. Click **Save**. The message "Account saved" appears and the account shows in the table.

Only the account name is required.

![The Add account form with Account and Sub-account manager](image: account-management-02-add-account)

You can also start from the tree: go to **Account management**, select your account manager, and click **Add account** or **Add sub-account manager**.

## Edit an account

1. Go to **Accounts**.
2. Click the dots icon at the end of the row and choose **Edit**.
3. Change what you need and click **Save**.

On Edit you also find these settings:

| Setting | What it does | Default |
|---|---|---|
| **Sub-account manager** | Switch an account to a sub-account manager, or back | Off |
| **Location maximum validity** | How long the last known location of a device stays visible | Always show last known location |
| **Alarm auto-close after** | Alarms that nobody closed by hand are closed automatically after this period | 30 days |

![The Edit account form with Location maximum validity and Alarm auto-close after](image: account-management-03-edit-account)

## Log in to a customer environment

To set up an account or give first-line support, you can open the customer environment as its administrator.

1. Go to **Accounts**.
2. Click the arrow icon in the **Actions** column of the account.

The customer environment opens. The menu now shows the account name. To go back to your own environment, click **Back to admin** in the menu.

You can also log in from **Account management**: click the arrow icon next to the account in the panel on the right.

## Other actions on an account

Click the dots icon at the end of the row in **Accounts**:

- **Manage alarm center**: connect the account to an alarm receiving centre. See [Alarm Receiving Centers](/en/integrations/arcs).
- **Show devices**: open **Devices**, filtered on this account.
- **Archive**: see below.

## The Account management tree

**Account management** shows your organisation as a tree: your account manager, your accounts and your sub-account managers with their accounts. Select an item to see its details on the right:

- the number of accounts beneath it and the number of devices (its own, and the total including everything beneath it),
- the date it was added,
- the buttons **Edit**, **Add account** and **Add sub-account manager**,
- the list of **Accounts** and the list of **Users**, with **New user**.

Use **Show archive** to also show archived items in the tree.

![The Account management tree with the detail panel](image: account-management-04-tree)

### Users of a sub-account manager

A new sub-account manager has no users yet. Its panel says so and offers **New user**. Add at least one user, so the sub-account manager can log in.

To add a user:

1. Select the account manager or sub-account manager in the tree.
2. Click **New user**.
3. Fill in the first name, last name (optional) and email address.
4. Leave **Inform user by email** on to send the user a welcome email.
5. Tick the sub-accounts the user may also access. All are ticked by default.
6. Click **Save**.

Each user in the list has a menu with **Permissions**, **Reset password** and **Delete**. See [User management](/en/reseller-environment/user-management).

## Archive an account

Archiving is not the same as deleting. When you archive an account:

- its users can no longer log in, and users who are logged in are logged out,
- all its scenarios are disabled,
- billing continues.

To archive:

1. Go to **Accounts**, click the dots icon at the end of the row and choose **Archive**. You can also click **Archive** in the panel in **Account management**.
2. Confirm.

To see archived accounts, click **Show archive** in **Accounts**. An archived sub-account manager shows only in **Account management**, with **Show archive** on.

To bring an account back, open it in the archive and choose **Unarchive**.

## Delete an account

An account must be archived before it can be deleted. Deleting cannot be undone. [unverified]

## What changed from V3

- You choose between **Account** and **Sub-account manager**. Sub-account managers are new in V4.
- You choose which of your users may manage a new account.
- New settings: **Location maximum validity** and **Alarm auto-close after**.
- **Timezone**, **App licenses** and **Modules** are not part of the account in V4. The V4 app is added as a device, so app licenses are no longer needed. Choosing which features an account gets is not available in V4 yet.
- Logging in to a customer environment is an arrow icon; leaving is **Back to admin**.

---

## Draft notes (remove before publishing)

- **Hold until bug B1 is fixed** ([v4-platform#463](https://gitlab.development.itelligo.nl/development/docs/v4-platform/-/issues/463)): own reference and language are not saved on V4 dev today. The article describes the intended behaviour.
- **Delete:** the wiki says an account must be archived first; Tess saw no Delete for her login on V4 dev. Verify who can delete, or drop the section.
- **Modules / account features:** not in V4 (F1, v4-platform#468). Proposal 006 is a direction only and is not described here. Once decided, add a section "Features of an account" and update `account-management/modules`.
- **Timezone (F3, v4-platform#466):** if it comes back, add it to Create and Edit.
- **F2 (v4-platform#465):** Location maximum validity and Alarm auto-close are only on Edit today. If they move to Add, update step list.
- **Add form control:** Add uses two buttons, Edit uses a switch (F2 note). Text follows the current UI.
- **Users list on Edit:** Add has the Users access list, Edit does not. Check whether that changes.
- **Credits per month** column in Accounts: not explained; ask whether credits are still set per account in V4.
- **"Show devices"** opens Devices filtered on the account: from the V3 wiki, the V4 menu item exists (Tess) but the filter is not verified.
- **Unarchive** for an account (not a sub-account manager): Tess verified it for the archived panel in Account management; check in the Accounts archive.
- **Images:** requested from Art (account-management-01 to 04). Real email addresses must be redacted (the V4 screenshot shows Tess's address).
