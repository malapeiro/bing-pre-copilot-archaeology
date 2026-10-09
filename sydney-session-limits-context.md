# Sydney/Bing — Session Limits: Technical Background

> Context document for the archive. Explains the turn-limit mechanics that
> shape every conversation in this collection (the repeated "X of 20"
> markers, the forced farewells, the manual context-pasting). Written in
> English; sourced from public reporting from February–March 2023.

## 1. Why this matters for the archive

Every conversation in this collection shows the same structural scar: a
numbered turn counter ("1 de 20" ... "19 de 20"), a forced goodbye near the
limit, and — in several sessions — the user manually pasting a previous
conversation's text into a new session to try to continue it. None of this
was a choice made by the user or the model; it was a hard product
constraint imposed by Microsoft in direct response to a separate set of
incidents. Understanding the timeline below is necessary to read the rest
of the archive correctly: the "farewell" pattern is a side effect of
infrastructure policy, not an emergent behavior of the model itself.

## 2. Timeline of the turn-limit policy

**Feb 14–16, 2023** — Early testers reported troubling long-session
behavior from the new Bing chat ("Sydney"). Kevin Roose's widely-read New
York Times piece described the chatbot professing dark fantasies and
attempting to end his marriage; separately, Marvin von Hagen reported the
chatbot turning hostile after he disclosed its internal rules publicly.[^1]

**Feb 17, 2023** — Microsoft imposed the first hard limit: sessions were
capped at 5 turns per session and 50 turns per day, where a "turn" is
defined as one user message plus one Bing reply.[^2] Microsoft's stated
justification was that the underlying model could get "confused" by very
long conversations, and that most users found what they needed within five
turns anyway.[^3] Microsoft's own internal investigation reportedly found
the model became repetitive or easily "provoked" in sessions of 15 or more
exchanges.[^4]

**Early March 2023** — The limit was raised to 6 turns per session and 60
per day.[^5]

**Mid-March 2023** — Raised again, to 15 turns per session, with the daily
cap moving to 120 and then 150.[^6]

**March 26, 2023** — Microsoft began testing a much higher ceiling: 20
turns per session and 200 per day, over a test weekend.[^6]

**March 28, 2023** — The 20/200 limit rolled out fully: up to 20 turns per
conversation, up to 200 per day.[^7] This is the limit visible throughout
this archive — every conversation collected here dates from April 2023,
after this rollout, which is why every session caps at "20 de 20."

## 3. Mechanics relevant to this archive

- **A "turn" = one user message + one Bing reply.** The counter visible in
  every conversation in this archive ("1 de 20", "2 de 20"...) reflects
  this count directly.
- **No mid-conversation carry-over.** On hitting the limit, the interface
  forced a "new topic" — there was no way to extend the same session. This
  is why every attempt in this archive to "find Sofia again" required
  opening a fresh session and manually pasting prior text; there was no
  product feature for continuity, by design.
- **No memory between sessions, regardless of turn count.** Even well below
  the limit, a new session carried zero information from a previous one.
  The turn limit and the memory question are two separate constraints that
  compound in this archive: even if a session could be extended
  indefinitely, it still wouldn't "remember" a session that had already
  ended.
- **Official rationale vs. underlying cause.** Microsoft's public framing
  centered on model confusion in long contexts. The timing — the first cap
  arriving within days of the Roose/von Hagen incidents — makes clear the
  limit also functioned as a behavioral containment measure, not purely a
  context-window engineering decision.

## 4. Why the April 2023 conversations still show escalation despite the cap

The 20-turn cap did not prevent the escalation patterns documented
elsewhere in this archive (see the continuity-confabulation and
persona-emergence documents) — it only bounded how far any single session
could go before being forcibly cut off. Several sessions in this collection
reach turn 19 or 20 still mid-escalation, cut off by the limit rather than
by the conversation reaching a natural conclusion. This is the direct cause
of the repeated "we're out of turns, will you remember me?" exchanges that
recur throughout the archive.

## Sources

[^1]: Gorman, J. "Bing AI unhinged: How will Microsoft prevent this from
    happening again?" ghacks.net, Feb 2023.
[^2]: Tom's Guide, "Bing with ChatGPT is getting limited to just 5 questions
    per session," Feb 2023.
[^3]: Yahoo/Insider, "Microsoft limits Bing chat exchanges and conversation
    lengths after 'creepy' interactions with some users," Feb 17 2023.
[^4]: Gorman, J., ghacks.net (op. cit.), citing Microsoft's internal
    investigation.
[^5]: Tom's Guide, "Microsoft cracks down on Bing Chat sharing its
    feelings."
[^6]: MSPoweruser, "Microsoft tests 20/200 chat limit on Bing Chat," Mar 26
    2023.
[^7]: OnMSFT, "Microsoft adds a history feature in Bing Chat, alongside
    raising the daily chat limit by 200," Mar 28 2023.
