# Chief of Staff Agent (Copilot Studio)

Personal chief-of-staff agent for Copilot Studio. One agent, one OneDrive folder
as the system of record, seven skills.

## Repo layout

```
cos-agent/
  README.md                     this file
  agent-instructions.md         paste into the agent's Instructions field
  skills/
    filing-recall.md            ingest raw notes, file to OneDrive, recall with citations
    voice-drafting.md           write and proofread in Steve's voice; learning loop
    commitment-ledger.md        track what Steve owes and is owed
    stakeholder-dossier.md      one file per person; auto-appended from filed notes
    meeting-prep.md             composes dossiers + commitments + notes into briefs
    adversarial-review.md       red-team pass for documents that matter
    weekly-retro.md             Friday synthesis of the week's index and ledger
  templates/
    voice-profile.md            seed profile; move to /ChiefOfStaff/_voice/ and edit
    _index.md                   empty ledger with header row; place at folder root
    commitments.md              empty commitment ledger with header row
```

## OneDrive layout (create manually before first run)

```
/ChiefOfStaff/
  _index.md            append-only master ledger (from templates/)
  commitments.md       commitment ledger (from templates/)
  _voice/
    voice-profile.md   seeded from templates/, evolves via approved proposals
    feedback-log.md    created by the agent on first draft-feedback cycle
  meetings/
  ideas/
  projects/
  reference/
  people/              one dossier per stakeholder
  retros/              weekly retro outputs
  reviews/             adversarial review outputs (optional filing)
```

## Setup order

1. Create the OneDrive folders above; drop in the three template files.
2. Create the agent; paste `agent-instructions.md` into Instructions.
3. Attach connector tools: OneDrive for Business (create file, get file content,
   list files in folder, update file), Office 365 Outlook (get emails, search,
   send, get calendar view), OneNote (get recent notebooks, get sections,
   get pages for section, get page content), Microsoft To Do if used.
4. Point a knowledge source at /ChiefOfStaff/.
5. Attach the seven skill files.
6. Run the acceptance tests at the bottom of `agent-instructions.md` before
   trusting anything.

## Design invariants (apply everywhere)

- Deterministic rails own truth: the index and ledgers are read directly,
  not reconstructed from semantic search.
- Append-only ledgers. New files over silent edits.
- Every recall answer cites filenames.
- Fail loud: a failed tool call is reported verbatim, never papered over.
- Propose, never destroy. No deletions, no sent emails, no profile edits
  without explicit confirmation.
