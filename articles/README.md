# Wiki article drafts

Markdown drafts for wiki.cuebly.com (Wiki.js), written by David van der Berg (wiki, cloud). Nothing here is published; Jarno approves every article first.

## Structure

The folders follow the wiki's own paths. `reseller-environment/account-management.md` becomes `https://wiki.cuebly.com/en/reseller-environment/account-management`.

## Each draft has

- A header block with the wiki path, title, description, status, sources and the date of the last fact check.
- The article text, in customer and reseller language: short sentences, task first.
- Images as `![alt text](/wiki-images/<set>/<file>.png)` with the caption in italics below. The images are Art's, in frontend-design `wiki-images/`, always built from Tess's real screenshots (team README, "Wiki images: the update loop"); alt text and captions come from Art's alt text files. When publishing, upload them to the wiki and adjust the path. An image that does not exist yet stays a placeholder `![alt text](image: <name>)`, requested from Art in `team/board/art.md`.
- A closing section **Draft notes (remove before publishing)**: what is not verified by Tess, open bugs that affect the text, and questions. Statements in the article that are not verified carry the mark `[unverified]`; remove the mark once checked, or remove the statement.

## Writing rules (Manon's review, 2026-10-21)

- **Current product only** (Jarno, 2026-10-21): no version names (no V3, no V4), no "What changed" sections, no comparisons with before. The configurator is called DevCon. Go-live is planned in `plan/cutover.md`; wiki changes are logged in `CHANGELOG.md`.
- **Describe what happens, not why**, unless Jarno, a ticket or the product notes say why. No invented intent ("this is on purpose so that...").
- **Do not document bugs or gaps as behaviour.** No workarounds for known bugs in the text. Put them in the Draft notes with the ticket id, and describe the intended behaviour once Jarno confirms it, or leave the point out.
- **"Good to know" only for what a customer really needs** to do the task right.

## Pattern: device behaviour

For how a device behaves in practice (what it sends when, how fresh its location is, what a setting changes), beyond the feature and configuration tables. First used for Twig and beacons (T18).

**Three levels, each fact in one place only:**

| Level | Where | Title | What goes there |
|---|---|---|---|
| General | `supported-devices/location-in-alarms` (new page) | How location reaches an alarm | Device-neutral: an alarm can arrive in more than one message, how old a location can be, the scenario option "wait for possible new location", following an alarm through the alarm link, periodic tracking. Links to the brand and model pages |
| Brand | the brand page, for example `supported-devices/personal-trackers/twig` | section **How Twig devices behave** | Behaviour shared by all models of the brand. Links to the general page |
| Model | the model page, for example `.../twig-one` | section **How this device behaves**, after "Configuration options", before "Settings to connect to the platform" | Only what differs for this model, or which brand behaviour applies to it. One line with a link if nothing differs |

**Each behaviour is one short block:**

```
### <What the user notices, as a plain statement>

<What happens, in two to four sentences.>

**What to do:** <the setting, scenario option or habit that helps>.

**Applies to:** <models, and firmware if known>.
```

- The heading is what the customer notices ("The first alarm message has no indoor location"), not a technical term.
- Setting names exactly as in DevCon and the configuration table, in bold.
- No "why" unless the manufacturer, Jarno or a ticket says it. Manufacturer statements that we have not tested say so: "According to Twig, ...".
- A manufacturer limitation is behaviour and may be documented. A Cuebly bug is not: it goes to the Draft notes with its ticket id.
- Every page or section with behaviour ends with one line: `*Last checked: <month year>.*`

**Staying current:**

- Each behaviour change gets a row in `CHANGELOG.md` with its source: test (Tess), ticket, release, or manufacturer firmware.
- Check the behaviour sections of a brand when its firmware changes, when a ticket touches alarms or location for that brand, and at least twice a year. Update the "Last checked" line, also when nothing changed.
- The `wiki-update` skill searches for "How this device behaves" and "How <brand> devices behave" when a device or location change comes in.

**Sections for live pages** that get no full rewrite are drafted as `<page>.section-<slug>.md` next to where the page would be (the header says `insert: after <heading>` on `<live path>`). They can go live on their own when Jarno approves, without waiting for the go-live.

**Sources:** a partner or customer report can be the reason for a section, but only its product facts are used, verified by Tess or confirmed by Jarno. No partner, customer or person names anywhere, also not in the Draft notes or the changelog ("a partner report" is enough).

## Status values

`draft` (written, not checked), `check` (waiting for Tess or Jarno on a fact), `review` (ready for Jarno), `approved`, `published`.
