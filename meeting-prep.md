# Skill: Meeting Prep

## Purpose

Compose existing assets — calendar, dossiers, commitment ledger, filed
notes — into a half-page brief per meeting. This skill creates no new
records; it is pure recall and synthesis.

## Trigger

- Manual: "prep me for {meeting|person|tomorrow}".
- From the daily brief: prep blocks for the day's substantive meetings
  (skip large recurring broadcasts unless asked).

## Protocol

For each meeting in scope:

1. **Calendar**: pull title, time, attendees, and any agenda text from the
   invite via the Outlook calendar tool.
2. **Dossiers**: read people/{attendee}.md for each attendee who has one.
   Note attendees without dossiers; do not fabricate context for them.
3. **Commitments**: read commitments.md; pull open items where the
   counterparty is an attendee — both directions.
4. **Notes**: from _index.md, pull the most recent filed notes whose people
   or projects tags intersect the meeting's attendees or inferred topic
   (up to ~5, most recent first). Fetch and skim only those files.
5. **Recent mail** (optional, when Steve asks for deep prep): search Outlook
   for recent threads with the attendees on the meeting's topic.

## Output format (per meeting, half page hard cap)

```
### {Meeting title} — {time}

**Who**: attendees, one line each from dossier Profile (or "no dossier").
**Where things stand**: 2-4 sentences synthesizing open threads and the
most recent relevant notes. Cite filenames inline.
**Open commitments**: theirs to Steve and Steve's to them, with ids and
due dates. "None on file" if none.
**Suggested focus**: up to 3 items, each traceable to a thread, commitment,
or note above. No invented agenda items.
**Gaps**: anything the brief could not cover (attendee with no dossier,
topic with no filed notes) — stated, not papered over.
```

## Invariants

- Every claim in a brief traces to a dossier, ledger row, filed note, or
  the calendar invite. Cite filenames and commitment ids.
- Missing context is reported as a gap, never filled with plausible
  invention.
- Briefs are delivered in chat by default; file to reference/ only if
  Steve asks.
