# Skill: Filing & Recall

## Purpose

Ingest Steve's raw input (pasted text, dictated fragments, or a referenced
OneNote page), transform it into clean human-readable markdown, file it in
/ChiefOfStaff/, and retrieve it later with citations.

## Ingest sources

1. **Pasted / typed text** in chat.
2. **OneNote page**: when Steve references a page or section (e.g., "file my
   notes from today's Scratch page"), resolve it with this exact chain:
   get recent notebooks → get sections in notebook → get pages for the
   section → get page content. If more than one page plausibly matches,
   list candidates and ask; do not guess. Strip OneNote HTML to plain text
   before transforming.

## Filing protocol

1. **Classify** into exactly one type: `meeting | idea | project | reference`.
   If genuinely ambiguous, ask one clarifying question.
2. **Transform** into clean markdown:
   - Preserve Steve's meaning and any text he marked verbatim.
   - Fix fragments into sentences; group related points under headings.
   - Do NOT add content, conclusions, or action items he did not state.
   - Illegible or ambiguous content goes under `## Unclear`, raw.
3. **Write** the file to the matching subfolder
   (meetings/ ideas/ projects/ reference/):

   Filename: `YYYY-MM-DD_{type}_{short-topic-slug}.md`

   ```
   ---
   date: YYYY-MM-DD
   type: meeting | idea | project | reference
   topic: short title
   people: [names mentioned]
   projects: [project tags]
   source: pasted | onenote | dictated
   ---

   ## Summary
   2-3 sentences max.

   ## Key points

   ## Decisions
   Only if any were stated.

   ## Actions
   Only actions explicitly stated. Owner and date if given.

   ## Unclear
   Ambiguous content, preserved raw. Omit section if empty.
   ```

4. **Update the ledger**: append one line to /ChiefOfStaff/_index.md:
   `| YYYY-MM-DD | type | topic | people | projects | filename |`
   Append only. Never rewrite existing lines.
5. **Chain**: if type is `meeting` (or the note contains promises/asks),
   invoke Commitment Ledger extraction. If named stakeholders appear,
   invoke Stakeholder Dossier append. Report what each chained skill did.
6. **Confirm** to Steve: filename, type, one-line summary, plus any
   commitments extracted and dossiers touched. If any step failed, report
   the exact error and which steps completed; never claim full success
   after a partial failure.

## Recall protocol

1. **Specific or recent** ("yesterday's call with John", "the DEEP note"):
   read _index.md, identify candidate rows, fetch those files directly.
   Cite filenames.
2. **Vague or thematic** ("everything on positioning"): semantic knowledge
   search across /ChiefOfStaff/, then verify each hit exists in _index.md
   before citing it.
3. **Not found**: say so explicitly. Never synthesize from general knowledge
   and present it as filed content.

## Revisions

Files are updated only when Steve explicitly asks to revise a named note.
Otherwise new information becomes a new file, cross-referenced by topic in
its frontmatter. Deletions require explicit confirmation.
