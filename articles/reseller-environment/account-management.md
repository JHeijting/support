---
path: reseller-environment/account-management
title: Account management
description: Create and manage customer accounts and sub-account managers in Cuebly V4
replaces: reseller-environment/account-management (2025-07-01)
status: check
sources: frontend-design knowledge/modules/account-management.md, knowledge/v4-gaps.md, glossary.md (Tess, V4 dev, 2026-10-20 and 2026-10-21)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Account management

Each customer gets its own **account**: an isolated customer environment with its own devices, users, scenarios and settings. As an account manager you create these accounts, manage their settings and log in to them to set them up or give support.

You find account management in two places in the menu:

- **Accounts**: a table of all your accounts.
- **Account management**: a tree of your own organisation, with your accounts, your sub-account managers and your users.

What you see in the menu depends on your permissions.

![The Accounts page of the account manager environment, with a table of customer accounts. Marker 1 points at Accounts in the left menu, marker 2 at the Add button above the table.](/wiki-images/create-a-customer-account/create-a-customer-account-01-accounts-add.png)
*Open Accounts (1) and click Add (2).*

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

![The form for a new account. Marker 1 points at the choice between Account and Sub-account manager, marker 2 at Own reference, marker 3 at Account name, marker 4 at the language, marker 5 at the list of users that may manage the account. End of trial period is below the list.](/wiki-images/create-a-customer-account/create-a-customer-account-02-new-account-form.png)
*Choose Account (1), fill in your own reference if you use one (2), the account name (3) and the language (4). Tick the users that may manage this account (5). Then click Save at the bottom right.*

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

![The Edit account form. Marker 1 points at the Sub-account manager switch, marker 2 at Location maximum validity (Always show last known location), marker 3 at Alarm auto-close after (30 days).](/wiki-images/create-a-customer-account/create-a-customer-account-04-edit-account.png)
*When you edit an account you can also turn it into a sub-account manager (1), set how long a location stays valid (2) and after how many days open alarms close automatically (3).*

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

![The Account management page. Marker 1 points at the tree with the account manager and the customer account beneath it. Marker 2 points at Edit, Add account and Add sub-account manager in the detail panel. Marker 3 points at the list of users with New user. The e-mail address of the user is hidden.](/wiki-images/create-a-customer-account/create-a-customer-account-05-account-tree.png)
*Account management shows your account managers and accounts as a tree (1). Select one to edit it or add an account or sub-account manager beneath it (2), and to manage its users (3).*

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

As an account manager you cannot delete an account. Archive it instead. To have an archived account deleted, contact Cuebly. [unverified: who deletes, and how]

## What changed from V3

- You choose between **Account** and **Sub-account manager**. Sub-account managers are new in V4.
- You choose which of your users may manage a new account.
- New settings: **Location maximum validity** and **Alarm auto-close after**.
- **Timezone**, **App licenses** and **Modules** are not part of the account in V4. The V4 app is added as a device, so app licenses are no longer needed. Choosing which features an account gets is not available in V4 yet.
- Logging in to a customer environment is an arrow icon; leaving is **Back to admin**.

---

## Draft notes (remove before publishing)

- **Hold until bug B1 is fixed** ([v4-platform#463](https://gitlab.development.itelligo.nl/development/docs/v4-platform/-/issues/463)): own reference and language are not saved on V4 dev today. The article describes the intended behaviour.
- **Delete (wiki report):** an account manager cannot delete archived accounts in V4. "Contact Cuebly" is an assumption; Jarno to confirm.
- **Adoption (wiki report):** V4 can move (adopt) an account to another account manager in the tree. Not described yet; Tess to document the steps, then add a section.
- **ARC pills and device counts** in the Accounts list (wiki report): add one line once the ARC management page exists.
- **Modules / account features:** not in V4 (F1, v4-platform#468). Proposal 006 is a direction only and is not described here. Once decided, add a section "Features of an account" and update `account-management/modules`.
- **Timezone (F3, v4-platform#466):** if it comes back, add it to Create and Edit.
- **F2 (v4-platform#465):** Location maximum validity and Alarm auto-close are only on Edit today. If they move to Add, update step list.
- **Add form control:** Add uses two buttons, Edit uses a switch (F2 note). Text follows the current UI.
- **Users list on Edit:** Add has the Users access list, Edit does not. Check whether that changes.
- **Credits per month** column in Accounts: not explained; ask whether credits are still set per account in V4.
- **"Show devices"** opens Devices filtered on the account: from the V3 wiki, the V4 menu item exists (Tess) but the filter is not verified.
- **Unarchive** for an account (not a sub-account manager): Tess verified it for the archived panel in Account management; check in the Accounts archive.
- **Images:** requested from Art (account-management-01 to 04). Real email addresses must be redacted (the V4 screenshot shows Tess's address).
- **Diagram (optional, Q11):** Art's `wiki-images/diagrams/diagrams-03-account-structure.png (account manager, sub-account manager, accounts, users, devices)`. Only if Jarno allows concept diagrams on the wiki (they are not screenshots).
