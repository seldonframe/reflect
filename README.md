# reflect — Bezos-level thinking on your toughest calls, in 5 minutes

Everybody decides. Billionaires *think it through* differently — and that
thinking process is written down. Bezos put his in his shareholder letters.
Warren Buffett and Charlie Munger spent 50 years explaining theirs. Farnam
Street turned it all into essays.

This turns those essays into something your AI actually **runs**.

You type one sentence:

```
reflect on: should I raise my prices?
```

Five minutes later you have:

- **A straight answer.** Not "here are some considerations" — an actual call,
  first thing you read, in plain words.
- **How sure it is** (a real number, like ~75%), so you know whether to act now
  or test first.
- **The exact next step**, so you're never left with analysis and no action.
- **"This flips if…"** — the 1-3 things that would change the answer, so you
  know what to watch instead of second-guessing forever.

## What you do vs. what you get

**You do:** type one sentence about the thing you're stuck on. Answer maybe one
question. That's it — no books to read, no frameworks to memorize.

**Your AI does:** the heavy thinking, the way the best decision-makers do it:

1. **First it asks: "can this be undone?"** Bezos's rule. If yes, you get a
   fast answer at ~70% information — because slow-deciding easy stuff is how
   companies (and people) stall. If it's a one-way door — real money, your
   reputation, people — it slows down and runs the full process: rebuild the
   logic from scratch, imagine the decision already failed and find what killed
   it, check what happens *after* the first thing happens, check the odds
   against reality instead of hope.
2. **It picks the right thinking tools automatically.** There are 23 in here
   (compacted from Farnam Street + Bezos's letters, all linked). You never
   choose one — every decision gets only the 3-8 that actually matter for it,
   so you get sharp thinking instead of a lecture.

## The part nobody else has: it keeps score

Every answer gets logged with a prediction and a check-back date. The next time
you run it, it **opens by confronting the scoreboard**:

> "Three weeks ago you predicted X would happen by now. Did it?"

When you were wrong, it writes down *why* in one line — and applies that lesson
to every future decision. So it doesn't just think for you; **it gets smarter
about YOUR patterns every month you use it.** Reading about mental models never
did that. That's the difference between a book and a coach.

## Install (30 seconds)

**Claude Code:**
```bash
git clone https://github.com/seldonframe/reflect ~/.claude/skills/reflect
```
Then say `reflect on <anything you're stuck on>`. Done.

**Cursor / Codex:** paste [PROMPT.md](PROMPT.md) into your `AGENTS.md`.
**ChatGPT / Gemini / Claude.ai:** paste [PROMPT.md](PROMPT.md) into custom
instructions or the top of a chat. Same loop, no setup.

## Don't know what to ask first?

[STARTER-QUESTIONS.md](STARTER-QUESTIONS.md) — 10 questions worth running this
week, like *"which recurring expense would I never approve if it were proposed
fresh today?"* and *"which 'safe' choice am I making to avoid blame rather than
to win?"* One a day, and by next month the scoreboard is working for you.

## Make it yours (2 minutes, biggest upgrade)

Copy `CONTEXT.md.example` → `CONTEXT.md` and tell it three things: decisions
you've already made (so it never re-argues them), what you usually decide on,
and how bold you want the answers. Every answer lands in *your* situation
instead of generic advice.

## Credits & sources

The thinking belongs to the thinkers. Every file links its source — almost all
[Farnam Street](https://fs.blog) essays (read the originals; they're excellent),
plus Jeff Bezos's shareholder letters. This repo is paraphrased compactions with
attribution, not copies. The loop, the routing, and the scoreboard are original.

---

Built by the team behind [SeldonFrame](https://github.com/seldonframe/seldonframe) —
an open-source platform where AI agents run your front office (calls, bookings,
CRM, follow-ups). Loops like this one are how we build it.
