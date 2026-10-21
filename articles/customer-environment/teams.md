---
path: customer-environment/teams
title: Teams
description: Group devices and app users into teams, and message a whole team at once
replaces: customer-environment/teams (2021-12-23)
status: check
sources: screenshot current/platform-v4/teams/01-team-card.png, wiki-report.md (teams row), qa/2026-10-21-night-findings.md (P18, P19), glossary.md (Connection, Availability), fact sheet 2026-10-21 (teams in the app)
last fact check: 2026-10-21
author: David van der Berg
---

# Teams

A team is a group of devices, including app users. Use teams to send a message to everyone in the team at once, as recipients in scenarios, and to show the team's status on a dashboard. App users see their own teams in the app under **Groups** > **Teams**.

A device can be in more than one team.

## Create a team

1. Go to **Teams** and click **New team**.
2. Type the team name.
3. Add the devices.
4. Save. [unverified: exact steps and button names]

## The team card

Each team is a card with its name and its members. A member with a green dot is online; a grey member is offline.

On the card:

- the pencil icon edits the team,
- the bin icon deletes it,
- the arrow icon sends a message to the team.

![The Teams page with one team card. The card shows edit, delete and send message icons and the devices in the team, each with a green status dot. Marker 1 points at the team card, marker 2 at the New team button.](/wiki-images/teams/teams-01-team-card.png)
*Each team shows its devices and their status (1). Click New team (2) to create a team. On a card, use the pencil to edit, the bin to delete and the arrow to send a message to the team.*

## Send a message to a team

Click the arrow icon on the team card, write the message and send it. The message reaches the members that are online and available, and that can show messages. [unverified: dialog steps and summary of recipients]

## Teams in scenarios

- Choose a team as recipient in the actions **Text message on device** and **Send assistance request**.
- The action **Change team** moves the device that started a scenario into or out of a team.

## Who counts as available

In team overviews, a member counts as available only when the device is online and the user has switched **Available** on in the app. See [Availability, presence and connection](/en/cuebly-app/availability-presence).

![Three separate states. Connection: is the device online; shown as a green dot on device cards and team chips and as Online in the app header. Availability: does the person want to receive messages and assistance requests; set with the switch on the app's Home screen. Presence: is the device inside a geofence; set by its location and shown on the geofence card as Present and connected or Absent or disconnected, and in the app under Groups, Locations. Together: for a message to everyone in a geofence, only devices that are present and available receive it. In team views a device counts as available only when it is online and its Available switch is on.](/wiki-images/diagrams/diagrams-04-connection-availability-presence.png)
*Connection, availability and presence are three different things.*

---

## Draft notes (remove before publishing)

- **Save then Delete in the same place** (P19): right after saving a new team, the Delete button appears exactly where Save was, so a second click deletes the team. Consider a warning in the article ("check before you click again") if this ships unfixed, or wait for the fix (proposal 002).
- **Name field without label** (P18).
- **Create steps:** Tess documented the card, not the full create flow. Verify the steps and button labels.
- **Message dialog:** the V3 page showed a summary of recipients before sending. Not verified in V4.
- **Images:** Art's `teams/teams-01-team-card.png`. It shows "Tess QA team"; Jarno's demo names question is open (Q6).
- Diagram `diagrams-04-connection-availability-presence.png` (Q11: diagrams welcome). Its check list: the last line (team views count a device as available only when online and available) follows Jarno, while F17 says the platform does not show availability yet; and the app still uses "Available" for presence (proposal 004).
