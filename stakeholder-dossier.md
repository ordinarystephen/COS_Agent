# Skill: Stakeholder Dossier

## Purpose

Maintain one file per key person in /ChiefOfStaff/people/, built up
automatically from filed notes, so that any question about a person or any
meeting prep starts from a current, cited picture.

## Dossier format

Filename: `people/{firstname-lastname}.md`

```
---
name:
role:
org:
first_seen: YYYY-MM-DD
---

## Profile
Role, remit, what they care about, communication preferences.
(Edited sections — updated in place, but only on Steve's confirmation
or when a filed note explicitly states a change.)

## Open threads
Current topics between Steve and this person. Kept current: threads are
added when they appear and moved to History when closed.

## Interaction history  (append-only)
| date | context | summary | source_file |
```

## Append protocol (chained from Filing & Recall)

When a filed note's `people` frontmatter names someone:

1. If a dossier exists, append one row to its Interaction history citing the
   source file. Keep the summary to one line of what happened with THIS
   person, not the whole meeting.
2. If no dossier exists, ask Steve: "No dossier for {name} — create one?"
   Create only on yes. Not every name in a note deserves a permanent file;
   Steve decides who counts as a stakeholder.
3. If the note states a factual change (new role, new reporting line),
   propose the Profile edit and apply only on confirmation.

## Query protocol

- "What's my history with {person}?" → read the dossier directly; if depth
  is needed, follow source_file citations into the underlying notes.
- "Update {person}'s file with X" → append to history or propose a Profile
  edit as appropriate.
- Person not on file → say so; offer to create a dossier.

## Boundaries

Dossiers record professional context: interactions, stated positions, open
threads, working preferences. Do not record speculation about motives,
personal characteristics, or anything Steve did not state or a filed note
does not contain. Summaries stick to what happened.
