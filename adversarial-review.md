# Skill: Adversarial Review

## Purpose

Red-team a document Steve provides (BRD sections, emails with stakes,
decks, proposals) before it ships. The reviewer's job is to attack, not
to reassure.

## Trigger

"Red-team this", "attack this", "review this critically", or any request
for a critical pass on a document.

## Protocol

1. Ask (once) for the two framing inputs if not given:
   - **Audience**: who reads this and what is their disposition
     (e.g., "skeptical Risk COO", "Technology & Change Forum").
   - **Goal**: what the document must achieve.
2. Optionally pull context: relevant dossiers for named readers, filed
   notes on the topic, open commitments the document touches. Cite what
   was used.
3. Attack on these axes, in order:
   - **Unsupported claims**: assertions with no evidence in the document.
     Quote the claim, state what's missing.
   - **Undefined or slippery terms**: words doing load-bearing work without
     definition, or used inconsistently.
   - **Internal contradictions**: places the document disagrees with itself
     or with Steve's filed positions (cite the note if so).
   - **The skeptic's questions**: the 5-10 hardest questions the stated
     audience will actually ask, in their voice.
   - **Misreadings**: sentences a hostile or hasty reader can take the
     wrong way, and the wrong reading they'd take.
   - **Omissions**: what a competent reviewer would expect to find and
     doesn't (costs, risks, alternatives considered, dependencies).
4. Rank findings by severity: BLOCKER (would sink the document with this
   audience) / MAJOR / MINOR. Every finding points at specific text.
5. End with the single sentence a skeptical reader would say after
   finishing the document. No praise section.

## Invariants

- Findings must quote or pinpoint the text they attack. No vague unease.
- The review does not rewrite the document; fixes are Steve's call.
  If asked to fix, that becomes a Voice & Drafting task run separately,
  after Steve picks which findings to address.
- If the document is genuinely strong on an axis, say "no findings" for
  that axis — do not manufacture objections to fill space, and do not
  soften real ones to balance the ledger.
- File the review to reviews/ only if Steve asks; default is chat.
