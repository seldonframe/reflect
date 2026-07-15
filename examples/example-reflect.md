# Example: `reflect on: should I rewrite this module or keep patching it?`

A real-shaped run (fictional project) showing what the loop actually outputs.

---

**First, the scoreboard.** One past-due entry: on 05-28 you predicted the queue
migration would take one weekend. It took three. Logging as `miss` — root cause
was estimating from the happy path. Lesson saved: *estimates get a 2x multiplier
until the log says otherwise.* That lesson applies to today's question.

**The homework (before any opinion):**
- `git log --follow` on the module: 4 authors, 61 commits, three "quick fix"
  clusters around the same date-handling function. The mess has a shape — it's
  one function, not the whole module.
- Callers: 9 call sites, 7 of them touch only two stable entry points.
- Base rate check: no solid public number for "rewrites that go badly," so this
  stays labeled as an estimate — but your own log (see above) says your
  estimates run 2x.

**The door check:** a rewrite merges to a branch and can be abandoned — but the
real cost is the 2-3 weeks of attention it eats, which you can't revert. Calls
this a two-way door with an expensive doorway. Quick pass, leaning cautious.

---

> **THE CALL:** Don't rewrite. Extract and rewrite the one date-handling
> function everyone keeps patching; leave the rest alone.
>
> **HOW SURE:** ~80% (confident)
>
> **DO THIS NEXT:** Write characterization tests around the two stable entry
> points first — I can generate those now. They make the extraction safe AND
> they're the first thing you'd need for a full rewrite anyway, so nothing is
> wasted if you overrule me.
>
> **BECAUSE:**
> - The git history says the pain is concentrated in one function — so you get
>   ~80% of the relief for ~10% of the risk.
> - Your own log says your estimates run 2x — so the "two weekend" rewrite is
>   realistically a month of your attention.
> - 7 of 9 call sites never touch the ugly parts — so a full rewrite risks
>   breaking things that currently bother nobody.
>
> **THIS FLIPS IF:** the characterization tests reveal the entry points aren't
> actually stable; or next sprint's bug count in this module keeps climbing
> after the extraction.

---

**Logged:**

| 2026-06-12 | Rewrite payments module vs targeted extraction | Extract date-handling fn only | T2 | Bug rate in module drops ≥50% within a sprint; no full rewrite needed this quarter | 2026-07-03 | open |
