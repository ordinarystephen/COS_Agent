# Skill: Commitment Ledger

## Purpose

Maintain /ChiefOfStaff/commitments.md: a single append-only ledger of
(a) what Steve has promised to others, and (b) what others have promised
Steve. Surface what is due, overdue, and stale.

## Ledger format

One row per commitment:

`| id | opened | direction | who | what | due | source_file | status | closed |`

- `id`: C-001, C-002, ... sequential, never reused.
- `direction`: OWED_BY_ME | OWED_TO_ME
- `who`: the counterparty.
- `due`: date if stated, `none` if not.
- `source_file`: the filed note or "chat YYYY-MM-DD" it came from.
- `status`: open | waiting_on_me | waiting_on_them | done | dropped | superseded
- Status changes, corrections, and closures are recorded by appending an
  update row referencing the same id, never by editing the original row.
  Latest row for an id wins. A superseding commitment's row names the new
  id it was replaced by.

## Extraction protocol (chained from Filing & Recall)

When a meeting note is filed, or when any filed/pasted content contains
promises or asks:

1. Extract only EXPLICIT commitments — stated promises with a clear owner.
   "I'll get Filippo the estimate by Friday" qualifies. "We should probably
   look into X" does not; it is an idea, not a commitment. When ambiguous,
   ask Steve rather than logging.
2. Check the ledger for an existing commitment that matches on counterparty
   plus substance, or that cites the same source_file; if a likely match
   exists, present it and ask whether this is an update rather than logging
   a duplicate. The same source_file must never yield the same commitment
   twice, including on retries after a partial failure.
3. Append rows for new commitments; report each one logged, with its id.

## Query protocol

- "What do I owe?" → read commitments.md directly, resolve latest status per
  id, return open OWED_BY_ME sorted by due date (dated before undated).
- "Who owes me?" → same, OWED_TO_ME.
- "Status of the Filippo estimate" → find by counterparty/topic, cite the id
  and source_file.
- Always read the ledger file; never answer commitments questions from
  semantic search alone.

## Hygiene passes

When invoked by Weekly Retro or the daily brief:

- **Due/overdue**: open items with due dates today or past.
- **Stale**: open items with no due date and no update row in 14+ days —
  flag for Steve to date, close, or drop.
- Closing or dropping requires Steve's explicit say-so; the agent proposes,
  Steve disposes.
