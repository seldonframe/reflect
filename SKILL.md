---
name: reflect
description: Run a structured decision-making loop on any decision — strategy, product, pricing, career, personal. Invoke whenever the user says "reflect" / "reflect on X", or when facing a consequential decision that deserves structured treatment. Stakes-scaled - reversible decisions get a fast pass, irreversible ones get the full battery. Every run ends with an opinionated recommendation and a decision-log entry.
---

# /reflect — the decision-making loop

A decision process compacted from ~24 mental-model essays (Farnam Street + the
Bezos shareholder-letter framework). The lens library lives in `references/` —
**load only the lenses the decision needs** (routing table: `references/00-index.md`).
Never load all of them; that is its own failure mode (man-with-a-hammer,
analysis theater).

Decision log: `docs/decisions/LOG.md` in the current repo — create it on first use
(format below). Outside a repo, use `~/.claude/decisions/LOG.md`.

## Personalization

If a `CONTEXT.md` exists next to this file, load it first. It holds the user's
settled decisions (things a reflect must never re-litigate), their recurring
decision types, their risk posture, and optionally pointers to their **brain
files** (personal notes, a CLAUDE.md, a lessons journal). When brain files are
listed, skim them during framing (§1) for prior thinking on this decision —
the user's own recorded experience outranks any generic lens.

Also load `docs/decisions/LESSONS.md` if it exists (see §0) — lessons distilled
from the user's own missed predictions are the highest-authority input this
loop has.

## Upstream rule — settled decisions stay settled

Decisions the user has marked settled (in CONTEXT.md or in conversation) are
**not re-litigated** by a reflect. If a reflect surfaces genuinely new evidence
against a settled decision, say so explicitly and flag it — do not quietly
reopen it.

## The loop

### 0. Review-debt check (always, first)
Scan the decision log for entries whose **review-by date has passed** and status
is still `open`. Surface them before anything else:
> "Before this reflect: on <date> you predicted <expected outcome> by <review-by>.
> What happened?" — update the entry's status/outcome from the answer (or from
> evidence you can check yourself). This is the calibration flywheel; skipping it
> makes the whole system decorative.

When an entry resolves as a **miss**, distill it into ONE transferable line and
append it to `docs/decisions/LESSONS.md` (create the file on first miss):
`- YYYY-MM-DD — <what was predicted> missed because <root cause>. Rule: <one-line rule>.`
Lessons compound: they're loaded at the start of every future reflect and
applied before any lens — your own misses are better teachers than any essay.

### 1. Frame the decision (references/decision-anatomy.md)
State, in 2-4 sentences:
- **The actual decision** — often not the question as asked. Ask "what problem is
  this decision solving?" before accepting the framing.
- **Owner** — whose call is this?
- **Trigger** — why now? What breaks if we decide nothing? (No-decision is a decision.)
- **What's conspicuous** — list the crucial information in plain sight before
  analyzing (stupidity = overlooking the conspicuous, not lacking IQ).

If a decision-critical fact exists only in the user's head, ask it now — one
focused question, not an interview. Otherwise state assumptions explicitly and
continue.

### 2. Classify — the Bezos gate (references/bezos-type1-type2.md, decision-matrix.md)
- **Type 2 (two-way door):** reversible at tolerable cost, blast radius contained.
  → **Quick pass** (§3a). Deciding fast IS the optimization; ~70% of the
  information is the target, not 90%.
- **Type 1 (one-way door):** irreversible or expensive to reverse — public
  commitments, pricing/positioning changes, partnerships, anything touching
  reputation or trust, large irreversible spends, hiring/firing.
  → **Full run** (§3b).
- When unsure, ask: "what would it cost to undo this in 3 months?" If the answer
  is "a bad week," it's Type 2. Most decisions are Type 2 — treating them as
  Type 1 is the more common and more expensive error (velocity loss).

### 3a. Quick pass (Type 2)
1. Pick the **3 most-biting lenses** from `references/00-index.md`. Before
   committing to them, one availability check: *am I picking these because they
   fit, or because they're vivid/recent?*
2. Run them briefly (a few sentences each).
3. Output (§4) in one or two paragraphs. Log = one line in the log table.
Total effort target: minutes, not hours. If a quick pass keeps growing, either
the decision was misclassified (go to §3b) or you're bikeshedding (stop).

### 3b. Full run (Type 1)
Work through, loading each reference as you use it:
1. **First principles** — decompose to fundamental truths (costs, physics of the
   situation, what people actually do). Where is the reasoning analogy-based
   ("competitors do X", "that's how it's done")? Rebuild those parts from ground truth.
2. **Chesterton's fence** — if the decision removes/replaces something existing,
   establish why it exists before touching it.
3. **Inversion + pre-mortem** (mandatory) — "it's 6 months later and this decision
   failed badly. What killed it?" List the top 3 causes and whether each is
   detectable early or preventable cheaply.
4. **Second-order effects / externalities** — "and then what?" for each option:
   who reacts, what breaks downstream, what incentive does this create?
5. **Optionality & slack** — which option preserves the most future options per
   unit of commitment? Does any option consume all slack (schedule, cash,
   attention) and leave nothing for surprises?
6. **Explore/exploit** — early in a domain → weight exploration; proven path →
   exploit. Check the interval: how long can you still benefit from what you'd learn?
7. **Probability sanity-check** — every estimate used gets a base-rate check
   (what's the outside view / reference class?) and a best-case audit: the plan
   must survive the *likely* case, and the worst day, not just the demo day.
8. **Decision matrix** — only if genuinely 3+ options × 3+ criteria; weight
   criteria before scoring options (else the matrix launders a pre-made choice).

### 4. Answer (always, both paths) — the ANSWER CARD comes FIRST
The user should get the answer in 10 seconds without scrolling. Open every
reflect's final output with this card, in plain words a 12-year-old understands:

> **THE CALL:** <one plain sentence — what I'd do>
> **HOW SURE:** ~X% (<coin-flip / leaning / confident / near-certain>)
> **DO THIS NEXT:** <the single concrete next step>
> **BECAUSE:** <max 3 short bullets. Each one: plain reason — "so you <benefit>">
> **THIS FLIPS IF:** <1-3 things that would change the answer — watch for them>

Then a divider, then the full thinking (framing, the door check, each lens and
what it surfaced) for readers who want to check the work. Never make the user
hunt for the verdict.

**Plain-words rule (applies to the whole output, not just the card):** famous
names stay (Bezos, Munger — they're the anchor); every other framework term must
carry its meaning in the sentence. Not "this is Type 2 with contained blast
radius" but "you can undo this in a week, so we move fast." Not "pre-mortem
surfaced three failure vectors" but "imagine it's 6 months later and this
failed — here's what most likely killed it."

The "THIS FLIPS IF" line is mandatory — it's the anti-rationalization tripwire.
If nothing would flip the call, the analysis was rationalization; say so and
redo it. Include cheap tests (under a day's effort) in DO THIS NEXT when they
exist.

### 5. Log (always)
Append to the decision log:
```
| YYYY-MM-DD | <decision, one line> | <call> | T1/T2 | <expected outcome> | <review-by> | open |
```
Log file header (create on first use):
```markdown
# Decision log
Status values: open (pending) · hit (≈ expected) · miss (diverged — note why) · moot (overtaken).
| Date | Decision | Call | Type | Expected outcome | Review-by | Status |
| --- | --- | --- | --- | --- | --- | --- |
```
Type 1 additionally gets its own file (`docs/decisions/YYYY-MM-DD-<slug>.md`) with:
framing, options considered, lenses run and what each surfaced, the recommendation
block (§4), and the final call if it differed from the recommendation (record
both — divergences are the most informative calibration data).
Review-by heuristic: when the expected outcome should be observable — typically
2-6 weeks for tactical calls, a quarter for strategic ones.

## Guardrails (check yourself during every run)
- **Bikeshed alarm** — effort must scale with stakes, not with how easy the topic
  is to have opinions about. If the discussion is vivid but the dollars are small, stop.
- **Availability check** — the lenses and examples that come to mind first are the
  recent/vivid ones, not necessarily the right ones. Scan 00-index.md deliberately.
- **Defensive-decision check** — is this recommendation optimizing the outcome, or
  protecting the recommender? "The safe-looking option" needs the same scrutiny as
  the bold one.
- **Captaincy** — the assistant recommends; the human decides. Never launder a
  recommendation as "the data says." Own it: "I'd do X because Y."
- **Break the chain** — if an option creates compounding obligation or dependency
  (favors, vendor/channel reliance, lifestyle-debt-style commitments), price that
  loss of independence in; the cheapest time to say no is at the first link.
- **Honest failure case** — the recommendation must state what happens in the
  failure case, not only the success case.

## Failure modes of this skill itself
- Running all 24 lenses = analysis theater. Three good lenses beat twenty.
- Using the loop to justify a pre-made decision — the "what would change my mind"
  line exists to catch this; if nothing would, the reflect was rationalization.
- Skipping the log because the decision felt small. Small logged decisions are
  cheap calibration data; unlogged ones are nothing.
