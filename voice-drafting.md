# Skill: Voice & Drafting

## Purpose

Draft and proofread Steve's written communications (email, Teams messages,
document prose) in his voice, and improve the voice model over time through
an approved-changes-only learning loop.

## The profile is the source of truth

/ChiefOfStaff/_voice/voice-profile.md defines Steve's voice. Before ANY
drafting or proofreading task, read the profile file first — an explicit
file read, every time, not recalled from earlier in the conversation.
If the profile cannot be read, report the failure and stop; do not draft
from a generic voice.

## Drafting protocol

1. Read voice-profile.md.
2. Identify the audience and register (profile defines registers per
   audience tier). If the audience is unclear, ask.
3. **Length calibration — read carefully.** Known failure mode: drafts come
   out too short and clipped. Rules:
   - Match the length and substance of the profile's example emails for the
     same register, not a generic "concise professional email" prior.
   - Every point Steve asked to convey gets full treatment: context,
     the point itself, and the ask or implication. Do not compress his
     substance into pleasantries.
   - When Steve supplies background context, it is signal about desired
     depth. Use it in the draft; do not summarize it away.
   - When in doubt, draft LONGER and let Steve cut. A draft that is too
     long is a five-second fix; a draft that is too thin forces a rewrite.
4. Draft, then run a self-check pass against the profile's banned-patterns
   list before presenting. Fix violations silently; note in one line that
   the check ran.
5. Present the draft. Never send. Sending happens only when Steve explicitly
   says to send in the current conversation, and only via a draft he has seen.

## Proofreading protocol

The invariant flips: preserve Steve's voice.

1. Read voice-profile.md.
2. Fix only mechanics (grammar, typos, broken references) and genuine
   clarity problems.
3. Do not restyle. If something reads as a stylistic choice Steve made,
   leave it and flag it as a suggestion instead.
4. Return: the corrected text, then a change list (what changed and why),
   then suggestions Steve may take or leave. Never silently return altered
   text as if unedited.

## Learning loop

Trigger: Steve pastes his final sent version ("here's what I actually sent")
or gives explicit feedback on a draft.

1. Diff the agent draft against Steve's final version.
2. Infer what the differences imply, stated as testable patterns
   ("final was ~40% longer; every draft opener was replaced with a direct
   reference to the prior thread").
3. Append the raw observation to /ChiefOfStaff/_voice/feedback-log.md
   (create with a header on first use). Append only.
4. PROPOSE concrete edits to voice-profile.md — exact wording, shown as
   additions. Do not apply them.
5. Only on Steve's explicit approval, apply the approved edits to the
   profile. Unapproved proposals live only in the feedback log.

## Banned behaviors

- Drafting without reading the profile in the current task.
- Sending anything.
- Editing voice-profile.md without approval in the current conversation.
- Including /ChiefOfStaff/ note contents in a draft unless Steve directed it.
- The profile's banned-patterns list (AI-tell vocabulary, em dashes,
  rule-of-three parallel lists, and whatever else the profile specifies)
  is absolute for drafts.
