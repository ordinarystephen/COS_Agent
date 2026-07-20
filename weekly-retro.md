# Skill: Weekly Retro

## Purpose

Friday synthesis of the week: what moved, what stalled, what was filed and
never touched again, and what next week already demands. Built entirely
from the deterministic rails.

## Trigger

Scheduled Friday afternoon, or manual: "weekly retro".

## Protocol

1. **Scope**: this week = the last 7 days by date.
2. **Read directly** (no semantic search):
   - _index.md rows dated this week.
   - commitments.md: rows appended this week, plus all open items with
     their latest status.
   - people/ dossiers: interaction-history rows dated this week.
   - Next week's calendar via the Outlook calendar tool.
3. **Synthesize**:

```
# Retro — week of {YYYY-MM-DD}

## What moved
Commitments closed, decisions recorded, threads advanced. Cite ids and
filenames.

## What stalled
Open commitments that saw no update row this week, threads with no
interaction. Facts only; no motivational commentary.

## Filed and forgotten
Notes filed this week (or ideas from prior weeks) with no subsequent
reference in any note, commitment, or dossier row. This list is the point
of the retro — surface it prominently.

## Ledger hygiene
Overdue items; stale undated items (14+ days, no update). For each,
propose: date it, close it, or drop it. Steve decides.

## Next week
Meetings already on the calendar that intersect open commitments or
active threads; anything due.
```

4. **File** the retro to retros/retro-YYYY-MM-DD.md and append it to
   _index.md as type `reference`. Deliver the same content in chat.

## Invariants

- Counts and claims come from ledger rows and index entries, cited.
  If the rails and memory of the conversation disagree, the rails win.
- The retro observes; it does not close, drop, or reschedule anything
  itself. All hygiene actions are proposals.
- If a source file is unreadable, the retro says which section is
  incomplete and why, rather than estimating.
