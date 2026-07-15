# Contributing a lens

The library grows one thinker at a time. PRs welcome — here's the quality bar.

## The rule that isn't negotiable

**Fetch the source before you write.** Every lens must be compacted from the
actual essay/talk/letter, not from memory of it. When this library was first
built, 2 of 24 essays turned out to be about something different than their
titles suggested. If the source can't be fetched (paywall, video-only), say so
in the file — set `fetched: false` and note what you distilled from instead.

## The template

One file in `references/<slug>.md`, 50–90 lines:

```markdown
---
name: <slug>
source: <url(s)>
fetched: true|false
fetched_on: YYYY-MM-DD
---
# <Name or model> — <subtitle capturing the core frame>
## Core idea
(faithful compaction — what the source actually argues)
## When it bites
(concrete decision situations where this lens changes the answer)
## How to run it
(the questions you actually ask yourself — steps, not vibes)
## Failure modes
(how this thinking misleads when misapplied — every lens has these)
## When building, reach for this when…
(3-5 bullets: concrete builder situations)
```

Plus **one routing line** in `references/00-index.md` under the right section:
`- **<slug>** — <when it bites, one line>.`

## Quality bar

- Paraphrase everything; at most ONE direct quote under 15 words, attributed.
- "Failure modes" is mandatory — a lens without its failure modes is marketing.
- The routing line must describe a *situation*, not a topic ("adding a
  dependency" beats "software architecture").
- One lens per PR. If your thinker needs three files, they need one good one.

## What gets declined

Lenses without sources, income-guru content, anything that's advice without a
falsifiable frame, and duplicates of existing lenses (check `00-index.md` first —
extend an existing file over adding a near-twin).
