---
path: supported-devices/location-in-alarms
title: How location reaches an alarm
description: Why the first alarm message can lack the indoor location, how old a location can be, and how to make sure alarm messages show a recent location
status: check
sources: partner report (product facts only) and Jarno's answers, 2026-10-22 (T18); scenario actions draft; wiki page supported-devices/personal-trackers/twig (beacon age). Waiting for Tess's fact check (T18).
last fact check: 2026-10-22 (not yet tested)
author: David van der Berg
---

# How location reaches an alarm

When someone raises an alarm, the device sends what it knows at that moment. A newer or more precise location, for example the indoor location from beacons, can follow a moment later. This page explains what that means for your alarm messages and what you can do.

## The first alarm message may not have the latest location

Some devices send an alarm in two steps. The first message goes out at once, with the location the device has at that moment. Indoor location (beacons) or a new position can follow in a later message.

The alarm in **Alerts** shows the newer location as soon as it arrives. A scenario action that runs on the first message does not: it uses the location of the first message.

**What this means for scenario actions:** an **Email**, **Sms message** or **Send assistance request** that runs on the alarm can show an older location, or no indoor location at all, while the alarm in the platform shows the right one a moment later.

**What to do:**

- Follow an alarm up through the alarm in **Alerts** or the **LIVE LOCATION URL** in your message. They always show the most recent location. [unverified: name of the alarm link]
- Use the location placeholders in a message as a first indication, not as the final location.
- If your message uses a location placeholder, tick **Wait for possible new location**. The message then waits a short time for a newer location. This often helps, but it depends on timing and is not guaranteed. [unverified: option name and behaviour]

## A location can be older than the alarm

A device does not always measure its location at the moment of the alarm. It can send the last location it knew, for example the last beacon it saw. How old that location can be depends on the device and its settings. See the device page, section **How this device behaves**, for example [Twig](/en/supported-devices/personal-trackers/twig).

Any device can move after the alarm, or get a better location. That is another reason to follow the alarm through the alarm itself or the live location link.

## Keep locations recent

- Switch on **periodic tracking** for devices whose location others rely on, for example when beacon information is shown on the screen of other devices. The device then sends its location regularly, not only when there is an alarm. [unverified: setting name in DevCon]
- Check the device page for settings that make the location in the first alarm message more recent.

*Last checked: October 2026.*

---

## Draft notes (remove before publishing)

- **Source:** a partner report (only product facts used, no names) and Jarno's replies. Facts 1 to 5 of T18. Fact 6 (Twig working on the same freshness without beacons on the display) is left out until confirmed.
- **Alarm link name:** once Tess confirms it, write it as the customer sees it in the message, not in capitals like a code (Manon's review).
- **Waiting for Tess (T18):** the two steps, the "Wait for possible new location" option (label and whether it exists on the current platform; the scenario actions draft left it out as unverified), the name of the alarm link (is it LIVE LOCATION URL, or a separate alarm URL?), and the periodic tracking setting name.
- **Device-neutral on purpose:** the general page says "some devices". Only Twig is confirmed. Add other brands to their own pages when their behaviour is known.
- **Placement:** new page under supported-devices. Add a link from `customer-environment/scenarios/actions` (location placeholders) and `customer-environment/alerts` when they go live.
- **May go live before the go-live** (Jarno, T18): no version names, true today.
