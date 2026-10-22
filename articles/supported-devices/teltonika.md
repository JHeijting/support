---
path: supported-devices/teltonika
title: Teltonika
description: What all Teltonika devices share, and how to connect them to Cuebly
status: draft
sources: live pages teltonika-tmt250 (id 14), teltonika-gh5200 (id 15), teltonika-fmc640 (id 85), teltonika-fmc650 (id 86), downloads (id 3), read 2026-10-22; brand page structure (J16)
last fact check: 2026-10-22
author: David van der Berg
---

# Teltonika

Teltonika makes personal alarms and vehicle and I/O gateways. All Teltonika devices connect to Cuebly the same way.

## Models

| Model | Type |
|---|---|
| [TMT250](/i/14) | Personal alarm |
| [GH5200](/i/15) | Personal alarm |
| [FMC650](/i/86) | Gateway |
| [FMC640](/i/85) | Gateway (end of life, successor FMC650) |

## Connect to the platform

Configure the device over the air from the Cuebly platform, or with Teltonika's configuration software (see [Downloads](/i/3)). The device must be awake and able to connect over the internet.

These settings are the same for every Teltonika model:

| Setting | Value |
|---|---|
| Server URL | app.cuebly.com |
| Port | 8485 |
| Protocol | TCP |
| ACK type | TCP/IP |
| Sleep | disabled |

Each model page lists the other settings for that model, such as the APN for gateways.

---

## Draft notes (remove before publishing)

- New brand page (J16). No behaviour section yet: no Teltonika behaviour facts verified.
- Shared settings taken from the four live model pages; they match on all four. The protocol is written "Teltonika Codec 8" on TMT250 and FMC650 and "teltonika" on GH5200 and FMC640; left out until checked.
- "Over the air from the Cuebly platform": the live pages say "OTA configuration feature". Whether Teltonika devices are configured in DevCon today [unverified]; ask Tess before publishing.
- After this page exists, the model pages can drop the shared rows and link here (model page rewrite, later).
