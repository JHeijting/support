---
path: supported-devices/elexol
title: Elexol
description: ESPA 4.4.4 to IP converters, for example to receive fire alarms in Cuebly
status: check
sources: live pages elexol-ip2espa-v1 (id 87), elexol-ip2espa-v2 (id 88), gateways (id 84), read 2026-10-22; brand page structure (J16)
last fact check: 2026-10-22
author: David van der Berg
---

# Elexol

The IPtoESPA444 converters turn ESPA 4.4.4 messages into IP messages. Use them, for example, to receive alarms from a fire control panel in Cuebly. [unverified: Elexol as the manufacturer]

## Models

| Model | How it connects |
|---|---|
| [IPtoESPA444 V2](/i/88) | Has a web interface. Add the converter to Cuebly as a device, then enter the Cuebly device ID in the converter's web interface |
| [IPtoESPA444 V1](/i/87) | Needs a separate TCP/IP client with Cuebly software. Contact your account manager |

---

## Draft notes (remove before publishing)

- New brand page (J16). The live model pages never name the manufacturer; "Elexol" comes from their paths (`elexol-ip2espa-v1`, `-v2`). Jarno: is Elexol the right brand name? If not, the brand page gets the right name and slug.
- Inventory: ESPA2 cannot be imported from a file; one line on the model page, not here.
