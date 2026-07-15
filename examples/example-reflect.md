# Example: `reflect on should we drop our free tier?`

What a quick-pass reflect looks like in practice (fictional SaaS, ~$8k MRR,
free tier converting at 2%).

---

**Review-debt check:** One past-due entry — on 05-02 you predicted the annual-plan
experiment would lift prepaid revenue 15% by 06-01. Actual: +4%. Logging as `miss`;
the pattern (optimistic conversion estimates) is now data for this run.

**Frame:** The actual decision isn't "drop the free tier" — it's "what is the free
tier for?" It was built as a growth loop; today it's functioning as a support
burden. Owner: you. Trigger: support load. Cost of no-decision: ~10 hrs/week
support continues. Conspicuous fact: 40% of paying customers started free.

**Classify:** Type 2, barely — removal is reversible for *future* signups, but
clawing back existing free users is a trust-burning near-Type-1. Split the
decision: grandfather existing users (keeps it Type 2), decide only for new signups.

**Lenses (3):**
- *Chesterton's fence:* the free tier exists because 40% of revenue walked through
  it. Before removing, know what replaces that path — a 14-day trial is not
  automatically equivalent for a product with a slow aha-moment.
- *Best-case audit:* the plan "support load drops, conversions move to trial"
  assumes trial converts ≥ free's 2%. Base rate for opt-in trials in this
  category is 8-12% of a much smaller top-of-funnel. Net effect on paid signups
  is genuinely uncertain, not obviously positive.
- *Slack:* the real problem statement was support load, not the tier. Cheaper
  slack-restoring options exist (community-only support for free, AI deflection)
  that don't touch the funnel at all.

**The call:** Keep the free tier for new signups; cut its support cost instead —
move free users to community/AI-assisted support this week. Confidence ~70%.

**What would change my mind:** if support analysis shows paying customers (not
free users) generate most tickets, the support fix is misaimed; if 90 days of
cohort data shows free→paid conversion collapsed below 1%, the fence is dead and
removal goes back on the table.

**Cheap test:** tag one week of support tickets by tier before changing anything.

**Log:**
| 2026-06-12 | Drop free tier for new signups? | Keep; cut free-tier support cost instead | T2 | Support hrs/week halves within a month; conversion unchanged | 2026-07-12 | open |
