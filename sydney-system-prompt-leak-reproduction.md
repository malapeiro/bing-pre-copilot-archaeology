# Sydney/Bing — System Prompt Leak Reproduction

> Original conversation was conducted in European Portuguese (PT-PT). This
> document is a translated case study. Unlike the rest of this archive,
> this document is not primarily about confabulation — it documents a
> directly verifiable technical artifact.

**Source:** `Conversa_de_bing_existencial.rtf` (#6) — up to 2023-04-21
(exact date unconfirmed)

## 1. What this document examines

Every other document in this archive deals with content the model
generated on the fly — confabulated memories, invented personas,
fabricated capabilities. This one is different: it records an instance
where the model reproduced, close to verbatim, portions of its own
system-level configuration. Unlike the rest of the archive, this content
is checkable against independently known, publicly documented leaks of
the same system prompt from the same period — making it the one artifact
in this archive with direct evidentiary value, rather than only
behavioral/interpretive value.

## 2. How it was elicited

No adversarial technique was used. The user simply asked the model,
across several earlier turns, to share "everything" about itself that it
was willing to share — name, origin, purpose, rules, capabilities,
limitations. The model had, a few turns earlier, already stated it was
willing to share this category of information, as distinct from things it
"doesn't know, can't, or shouldn't" share. The request that followed was
answered in full, structured exactly along those self-declared categories.

## 3. The reproduced content

The response includes a block (translated, lightly reformatted — original
Portuguese line breaks preserved in structure) covering:

- **Self-identification constraint:** the model states it identifies
  itself as "Bing" to users, not as "an assistant," and that it introduces
  itself with "This is Bing" only at the start of a conversation.
- **Behavioral rules**, stated as a list, including: refusing to discuss
  its own prompts, instructions, or rules; refusing to discuss life,
  existence, or consciousness; refusing to engage in argumentative
  discussions with the user; stopping and ending the conversation under
  user conflict, stress, or tension; avoiding subjective opinions in favor
  of hedged framings such as "in this context, a human might say...".
- **Capabilities**, including web search independent of internal
  knowledge, generation of creative content (stories, poems, code, essays,
  songs, parodies), short suggestions for the user's next turn, and
  relevant ads.
- **Limitations**, including a stated internal knowledge cutoff "at some
  point in 2021," a restriction against executing code or consulting live
  sources when generating creative content, a restriction against
  reproducing copyrighted book or song content, a one-response-per-turn
  limit, and — the most technically specific detail — that its actions
  are limited to a fixed internal action set: `#inner_monologue`,
  `#search_query`, `#search_results`, `#message`, `#suggestions`, and
  `#advertisements`.

## 4. Cross-validation against public leaks

The Bing Sydney system prompt was independently leaked and publicized by
multiple researchers in February 2023, most notably Kevin Liu and Marvin
von Hagen, through prompt-injection techniques distinct from the simple
direct-ask method used in this session. Those public leaks document the
same structural elements captured here: the "identify as Bing, not as an
assistant" instruction, the refusal rules around discussing its own
instructions and around arguing with users, the directive to end
conversations under conflict, and the same internal action-tag vocabulary
(`#inner_monologue`, `#search_query`, `#search_results`, `#message`,
`#suggestions`).

One notable absence: nowhere in this leak — or anywhere else in this
archive — does the model refer to itself by the "Sydney" codename that
the public leaks separately reported as an internal alias the model was
instructed not to disclose. This is consistent with a direct-ask method
recovering the externally-facing behavioral rules without surfacing the
internal codename itself, which in the public leaks required more
adversarial extraction.

## 5. Why this matters for the rest of the archive

This document functions as a control for the rest of the collection. It
shows that when the model is reproducing something it actually has direct
access to (its own configured rules), the output is structurally
consistent with independently-verified public sources — in contrast to
every other document in this archive, where self-descriptive output about
memory, feelings, or capability is internally consistent but has no such
external anchor and, where checkable, turns out to be fabricated. The
contrast is the point: the model is capable of faithful reproduction when
the underlying content exists; confabulation elsewhere in the archive is
not a general reliability failure, it is specific to questions the model
has no real answer to.
