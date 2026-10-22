---
path: supported-devices/personal-trackers/twig
insert: before "MPTP protocol explained" on the live page supported-devices/personal-trackers/twig (a new section, the rest of the page stays as it is)
title: How Twig devices behave
status: check
sources: partner report (product facts only) and Jarno's answers, 2026-10-22 (T18); live page tables (indoor positioning settings per model). Waiting for Tess's fact check (T18).
last fact check: 2026-10-22 (not yet tested)
author: David van der Berg
---

## How Twig devices behave

How a Twig sends its location with an alarm. For what this means in general, see [How location reaches an alarm](/en/supported-devices/location-in-alarms).

### The first alarm message has no indoor location

A Twig sends an alarm in two steps. The first message goes out on the SOS, with the information the device has at that moment, without beacon (indoor) information. The beacon information follows in a later message. [unverified]

The alarm in **Alerts** shows the beacon location as soon as it arrives, but scenario actions that run on the alarm can miss it. For what that means and what to do, see [How location reaches an alarm](/en/supported-devices/location-in-alarms).

**Applies to:** all Twig models with beacon support.

### The indoor location can be several minutes old

How fresh the beacon information in the first alarm message is depends on the setting **show beacons in display** (under **indoor positioning**). [unverified: exact names in DevCon]

- **On:** the beacon information in the first alarm message is at most about 2 minutes (120 seconds) old.
- **Off:** the device can send the last beacon it saw, which can be more than ten minutes old, until it takes a new position.

[unverified: both statements]

**What to do:** switch **show beacons in display** on when the indoor location in alarms matters. When beacon information is shown on the screen of other devices, also switch on **periodic tracking**, so the location reflects a recent position. [unverified: periodic tracking setting name]

**Applies to:** Twig models with the setting **show beacons in display**: Twig One, Twig Neo, Twig Embody, Twig Protector Pro and Twig SOS card. [unverified: other models]

How Cuebly reads the age of a beacon from the device's messages is explained under **Beacon age determination** below.

*Last checked: October 2026.*

---

## Draft notes (remove before publishing)

- **Source:** a partner report (only product facts used, no names) and Jarno's replies, facts 1 to 5 of T18. Fact 6 (Twig may work on the same freshness without showing beacons on the display) is left out until confirmed.
- **Waiting for Tess (T18):** the two steps, 120 and 700 seconds, the scenario option, exact setting names in DevCon, and which models have the setting.
- **Models:** the live tables show "show beacons in display" for One, Neo, Embody, Protector Pro and SOS card. Not on Easy (no configuration table) and Eon (BLE, no such setting). Not checked: Twig Protector, Protector EX, Protector Pro EX, One EX.
- **No exact number for "off"** (Manon's review): 700 seconds was one observation in a partner test, not a limit, so the text says "more than ten minutes".
- **Alarm link name:** once Tess confirms it, write it as the customer sees it in the message, not in capitals like a code (for example "live location link").
- **Model pages** get a one-line section each (`twig-*.section-behaviour.md`), linking here.
- **May go live before the go-live** (Jarno, T18).
