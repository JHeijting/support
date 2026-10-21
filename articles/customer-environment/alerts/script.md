---
path: customer-environment/alerts/script
title: Close an alarm with the closing script
description: Handle an alarm step by step and record the outcome
replaces: customer-environment/alerts/script (2025-07-01)
status: check
sources: frontend-design knowledge/modules/alerts.md, glossary.md (Closing script), screenshots current/platform-v4/alerts/ (night test on V4 dev, 2026-10-21; Jarno)
last fact check: 2026-10-21 (updated with Tess's wiki report, T4)
author: David van der Berg
---

# Close an alarm with the closing script

The closing script guides you through an alarm step by step: what kind of alarm it is, who to call, and what the outcome was. It helps operators and security staff who handle alarms in their own organisation, and it records how long it took to close the alarm.

For a fast close without the steps, use **Quick close**. See [Alerts](/en/customer-environment/alerts).

## Start the closing script

1. Go to **Alerts** and open the alarm under **Open alerts**.
2. Click **Close alarm** and choose **Start closing script**.

![The detail of an open SOS button alarm with the Close alarm menu open. Marker 1 points at the Close alarm button, marker 2 at Start closing script. Quick close is the second option in the menu. On the right, the What happened timeline.](/wiki-images/handle-an-alarm/handle-an-alarm-02-close-alarm-menu.png)
*Click Close alarm (1) and choose Start closing script (2). Quick close closes the alarm without the script.*

## The steps

### 1. Introduction

The script starts with the alarm type and what to expect. For example: "This is an SOS button alarm. Expect an aggressive or medical situation."

It also shows the **panic word** and the **cancellation code** from the device's alarm protocol, when they are set.

Click **Start alarm handling**.

### 2. Call the device

The script shows the step **Call device**. Call the user of the device.

### 3. Choose the outcome

Ask the user what happened and offer your help. Then choose the outcome:

| Outcome | Use it when |
|---|---|
| **It was a false or test alarm** | The user confirms that nothing is wrong |
| **Verified alarm** | The user needs help |
| **Situation not (yet) clear** | You cannot tell yet what is going on |
| **No answer** | Nobody answered the call |

![The outcome step of the closing script, titled Offer your help and ask what you can do. Marker 1 points at the outcome buttons: It was a false or test alarm, Verified alarm, Situation not (yet) clear, and No answer.](/wiki-images/handle-an-alarm/handle-an-alarm-04-choose-outcome.png)
*Choose what happened (1). Then add your notes and click Close alarm.*

### 4. Notes and close

Add notes on what you did and what you agreed. Click **Close alarm**.

The alarm moves to **Closed alerts**. The closed alarm shows your notes and the **time to close the alarm**, in seconds.

## While you work

- **Show details** brings back the alarm information.
- The grey block at the bottom of the script keeps the key information in view: panic word, cancellation code, device name, customer, industry, operating address, and environment and risks from the alarm protocol.
- The arrow buttons next to the script take you one step back or forward.
- On the right, **What happened** shows the timeline of the alarm.

## Good to know

- The information in the script comes from the device and its alarm protocol. Fill in the device fields and link an alarm protocol to get the most out of the script. [unverified: alarm protocols in V4-only accounts]
- Alarms that nobody closes are closed automatically after the period set in **Alarm auto-close after** at the top of **Alerts** (30 days by default).

---

## Draft notes (remove before publishing)

- **Follow-up protocol not in V4 yet** (Jarno): the V3 script had steps for connection established, cancellation code check, guardians and emergency services. The article describes only what V4 does today. Extend when the follow-up protocol is built.
- **What each outcome leads to:** wiki report: not verified, the outcome is stored with the closed alarm. Ask Jarno before publishing.
- **Alarm protocols:** wiki report: no protocols menu in the V4 customer environment, but the device card has an "Alarm protocol" field. Check with Jarno where panic word and cancellation code are set in V4.
- **Discrete mode / silent alarm:** the V3 script had an extra listen step for devices in discrete mode. Not seen in V4.
- **ARC accounts:** in V3 the script runs automatically for alarm receiving centres. Not verified in V4.
- **Images:** requested from Art (closing-script-01, 02). Sources: `current/platform-v4/alerts/02-alarm-detail-close-menu.png`, `03-closing-script.png`, `04-closing-outcome.png` (this one has a text overlap glitch on the step title; ask Art to pick a clean frame or retake).
