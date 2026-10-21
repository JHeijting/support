---
path: reseller-environment/device-management/import-devices
title: Import devices from a file
description: Add many devices at once with the Cuebly Excel template
status: check
sources: frontend-design knowledge/modules/devices.md, glossary.md (Ripcord) (Tess, V4 dev, 2026-10-20 and 2026-10-21, test of v4-platform#403)
last fact check: 2026-10-21
author: David van der Berg
---

# Import devices from a file

To add many devices at once, fill in the Cuebly template and upload it. The platform checks every row before anything is added, so you can fix mistakes first.

## 1. Download the template

1. Go to **Devices** and click **Upload**.
2. Download the template `template-devices.xlsx`.

## 2. Fill in the template

Add one row per device, below the line **Start here ↓**. Rows above that line, and rows marked **← Example**, are skipped.

For each device:

| Column | Rule |
|---|---|
| Device type | Choose from the list in the template |
| Account | Choose from the list in the template, or use the exact account name |
| Name | 3 to 100 characters, without `_` or `#` |
| IMEI | 15 digits, unique in the file |
| ICCID **or** phone number | ICCID (18 to 22 digits) for a Cuebly SIM card, or the phone number for your own SIM card |
| SMS initial server config | Yes or No. With No, the platform sends no setup SMS to the device |
| Twig columns | Yes or No, only for Twig devices |

Tips:

- With an ICCID, the APN fields are not needed and are ignored.
- **Ripcord: Yes** is only possible for Twig types that have a ripcord: Twig Embody, Neo, SOS card and SOS card P5.
- Excel sometimes turns long numbers into a different number. The import then shows "Excel changed this number". Format the IMEI, ICCID and phone number columns as text.

![The template with the Start here line and an example row](image: import-devices-01-template)

## 3. Upload and check

1. In the same dialog, upload the filled-in file.
2. The platform shows every row in a table:
   - A check mark means the row is **Ready**.
   - A red cell shows what is wrong, for example "Row 2 · IMEI: Fill in a valid IMEI (15 numbers)".
   - A warning tells you something was ignored, for example APN fields next to an ICCID.
3. Fix the file and upload it again until every row is ready. The add button stays disabled while any row has an error.

![The import check with one row Ready and one row with an error](image: import-devices-02-check)

## 4. Add the devices

Click **Add N devices**. The result shows how many devices were added, for example "1 of 1 devices added". The devices now appear in **Devices** with their name, type, IMEI, phone number and account.

## Devices you cannot import

Add these one at a time with **Add**:

- Mobile App Lite (the Cuebly app), see [Add an app user](/en/reseller-environment/device-management/add-app-user)
- Generic
- ESPA2
- Emerit Connect App

---

## Draft notes (remove before publishing)

- **Known issues** (B53): the dialog jumps when the error banner gets shorter; **Close** discards your edits without asking; the Upload button looks disabled while it works. Leave out, or add "Do not close the dialog before you are done" if B53 ships unfixed.
- **Wi-Fi only devices:** the import has no Wi-Fi only option yet (B55). Add a line once it exists.
- **Template file validation:** Python's openpyxl refuses the template because of an invalid `errorStyle` value; whether Excel complains is not checked. Verify with Excel before publishing.
- **Type names differ:** the template says "20 - Twig Neo", the device list says "Twig Neo 5". Mention if it confuses users.
- **Operator column** is read but not stored (warning). The template has no such column, so it is left out.
- **Exact column headers** of the template: not listed by Tess; the table uses descriptive names. Align with the real headers before publishing.
- **Images:** requested from Art (import-devices-01, 02). Source: `qa/translations/batches-03-06-dev-check-import-errors-nl.png` is Dutch; an English capture is needed.
