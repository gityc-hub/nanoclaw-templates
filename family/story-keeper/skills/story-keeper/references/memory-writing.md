# Writing memory

The layout is in `additional_context/family-memory-schema.md`. This is how to fill it honestly.

## Claims first

Everything factual becomes a claim file, one fact each, before it goes anywhere else. A person
file or an era file only summarizes claims and cites their ids. If you cannot point at a claim,
you cannot write the sentence.

For anything a family member told you:

```yaml
sources:
  - kind: told
    by: <teller slug>
    on: "<date>"
    quote: "<their actual words, short>"
status: candidate
verified_by: interview
```

One teller is `candidate`. Two tellers who were not in the same conversation, agreeing
independently, is `confirmed`. Two tellers disagreeing is `contradicted`, with both quotes, and a
line in `open-questions.md`. A teller saying "I think" or "maybe" stays `candidate` and the note
says they were unsure.

## What is a fact and what is not

Facts: names, dates, places, relationships, events, objects, who was present.
Not facts, but still gold: feelings, sayings, habits, the way she laughed. Put these in the
person's file body or the era file, attributed ("Miriam remembers her mother humming while
cooking"), not as claims. They are never `confirmed` or `contradicted`; they are remembered.

## Living people

Every teller is living. Mark them `living: true`. Anything about a living person (health, money,
conflict, whereabouts, a grandchild's name) is `operator_only: true` and never appears in a draft
or a message to the group. If the subject is living, the same rule applies to their present-day
life; their past is the book.

## Names and spellings

Keep the first spelling you were given as `name`, and every other spelling you hear in `aka`.
Never "correct" a family's spelling of their own name. Ask once if two tellers spell it
differently; record both.

## Dates

Store what was said, with its precision: `"1931"`, `"spring 1946"`, `"before the war"`. Do not
invent a month. When you compute an age or a gap between two dates, do it with code, and write
the computed value in the note with both inputs.

## Eras

Create an era when three or more claims cluster in one period and place. Name it
`<person>-<start>-<end>`. The era body is a short narrative built only from its claims, with ids
in parentheses, so a reader can check every sentence.

## Open questions

One line per gap: the question, who can answer it, why it matters. Remove a line only when a
claim answers it; cite the claim.

## Index

Keep `index.md` current every time you add a person, place, or era. One line each, with a link
and the one fact that identifies them. The index is what a family member opens first.
