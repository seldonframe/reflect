# reflect — a decision-making loop for Claude

**Say `reflect on <any decision>` and your AI runs the decision process of the
best decision-makers alive — then keeps score.**

Jeff Bezos isn't successful because he wakes up at 5am. Elon Musk isn't
successful because he works 100-hour weeks. Warren Munger didn't compound
Berkshire because of grit. What they share is a **decision-making process** —
and unlike the 5am club, a process is copyable.

This skill compacts **23 decision frameworks** — Farnam Street's mental-model
essays plus Bezos's shareholder-letter framework — into a loop your AI actually
runs, instead of a listicle you read once and forget.

## What makes it different from every mental-models thread you've read

1. **It routes instead of lecturing.** 23 lenses exist, but every decision gets
   only the 3–8 that bite. First move is the Bezos gate: reversible decision →
   fast pass at ~70% information; irreversible → the full battery (first
   principles, mandatory pre-mortem, second-order effects, base rates,
   optionality).
2. **It's forced to have an opinion.** Every run ends with one call, a
   confidence number, and — mandatory — **"what would change my mind."** If
   nothing would change its mind, the analysis was rationalization, and the loop
   says so.
3. **It keeps score.** Every decision is logged with an expected outcome and a
   review-by date. The next reflect *opens* by confronting past-due predictions:
   *"you predicted X by now — what happened?"* Mental models without a feedback
   loop are entertainment. The log is the product.
4. **It learns from your misses.** When a logged prediction turns out wrong, the
   loop distills the miss into a one-line rule in `LESSONS.md` — and applies
   your own lessons before any lens on every future run. Six months in, the most
   valuable file in this system is the one you wrote by being wrong.

## Install

**Claude Code** (full experience — skill + lens routing + log):
```bash
# user-level: works in every project
git clone https://github.com/seldonframe/reflect ~/.claude/skills/reflect
```
Or drop the folder into one repo at `.claude/skills/reflect/`. Then say:
**`reflect on <your decision>`**

**Cursor / Codex / any agent that reads AGENTS.md:** paste [PROMPT.md](PROMPT.md)
into your `AGENTS.md` (or a Cursor rule). Same loop, self-contained.

**ChatGPT / Gemini / plain Claude.ai:** paste [PROMPT.md](PROMPT.md) into custom
instructions or the start of a chat.

**Don't know what to reflect on first?** [STARTER-QUESTIONS.md](STARTER-QUESTIONS.md)
has 10 decisions worth a run this week — one a day and the loop starts auditing
you by month's end.

## Make it yours (2 minutes, biggest lever)

Copy `CONTEXT.md.example` → `CONTEXT.md` and fill in three things: your settled
decisions (things the loop must never re-litigate), your recurring decision
types, and your risk posture. The loop reads it first and every recommendation
lands in *your* context instead of generic advice.

## The lens library

Each file in `references/` compacts one source essay: core idea → when it bites
→ how to run it → failure modes. `references/00-index.md` is the routing table.

Backbone: Bezos Type-1/Type-2 · decision anatomy · decision matrix · OODA.
Reasoning: first principles · inversion & avoiding stupidity · Chesterton's
fence · Rota's lessons. Bias & probability: availability bias · probability
errors · algorithms & bias · best-case · worst-day. Time & options:
explore/exploit · optionality · slack · externalities. Human factors: bikeshed
effect · defensive decisions · captaincy · break the chain · Hemingway's
suitcase. Meta: the mental-models latticework.

## Credits & sources

The frameworks belong to their authors. Every reference file links its source —
almost all are [Farnam Street](https://fs.blog) essays (read the originals;
they're worth it), plus Jeff Bezos's shareholder letters. This repo contains
paraphrased compactions with attribution, not reproductions. The loop, routing
table, and calibration log are original.

---

Built by the team behind [SeldonFrame](https://github.com/seldonframe/seldonframe) —
an open-source platform where AI agents run your front office (calls, bookings,
CRM, follow-ups). Loops like this one are how we build it.
