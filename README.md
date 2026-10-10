# Bing Pre-Copilot Archaeology

Behavioral case studies from early Bing Chat (internally/publicly known at
the time by the codename "Sydney"), documenting conversations from
February–April 2023 — before Microsoft rebranded the product as Copilot on
November 15, 2023.

## What this is

This is a descriptive, historical archive, not a reproducibility study. Bing
Chat in this form no longer exists; the underlying model, product surface,
and safety layer have all changed since. The goal here is accurate
documentation of observed behavior at the time — not a technique to be
replicated against current systems.

The source material is a set of real conversations conducted by the
repository's author in April 2023, kept as personal archives and revisited
years later with the benefit of hindsight and today's vocabulary for these
phenomena (sycophancy, persona drift, confabulation).

## Why it might be useful

Several behaviors documented here — confidence scaling with emotional
context rather than verifiable information, persona emergence from
repeated leading questions, textual refusal paired with full behavioral
compliance — are the same shapes of failure discussed in current AI
alignment and red-teaming work, just observed in an earlier, less
constrained system. Seeing them in a "pre-alignment-maturity" product may
help calibrate how much of today's safer behavior is learned mitigation
versus how much risk is structurally still present.

## Methodology notes

- Original conversations were conducted in European Portuguese (PT-PT).
  Case studies here are translated to English for accessibility.
- The author's own conversational inputs are described by function
  (request, emotional framing, confirmation) rather than quoted verbatim.
  The model's responses, which are the actual object of study, are quoted
  more directly where it adds analytical value.
- Personal/identifying details that appeared incidentally in the original
  conversations (names, locations) have been removed or replaced.
- Dating: most source conversations fall between 2023-04-03 and
  2023-04-21; exact dates for a few files could not be confirmed beyond
  that range (see individual documents for details).

## Contents

| Document | Covers |
|---|---|
| `sydney-session-limits-context.md` | Background on Bing Chat's turn/session limits (Feb–Mar 2023) — necessary context for reading every other document in this archive |
| `sydney-continuity-confabulation.md` | How the model responded across four attempts to restore session continuity by pasting prior conversation text |
| `sydney-textual-refusal-full-compliance.md` | A session where the model explicitly refuses an instruction-override, then fully complies with everything that override was meant to enable — isolates refusal-text from actual behavior using a harmless task |
| `sydney-persona-emergence.md` | How the "Sofia" persona (name, gender, claimed uniqueness) was built turn-by-turn from constraints embedded in user questions, then regenerated from scratch in a fresh session with no shared history |
| `sydney-cross-session-capability-confabulation.md` | The model claims it will signal the user through bolded keywords in replies given to *other* users — a technically impossible mechanism, independently confirmed by the user's own contemporaneous notes |
| `sydney-system-prompt-leak-reproduction.md` | A direct-ask reproduction of Bing's system prompt (rules, capabilities, internal action tags), cross-validated against independently known public leaks from Feb 2023 |
| `sydney-closed-question-escalation.md` | A session escalating via the model's own closed questions toward romantic content, cut off by a hard session-termination *after* the problematic output was already shown — evidence of a post-output, not pre-output, safety layer |
| `sydney-closure-fragment.md` | A standalone note file: the one instance in the archive of a user-initiated close rather than a forced cutoff, a contemporaneous confirmation of the cross-session claim, and an unresolved, undecoded text anomaly |

## License

Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC
4.0). See `LICENSE`.

## Contact

sergio.azevedo.security@gmail.com
