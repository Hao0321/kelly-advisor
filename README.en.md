# Kelly Advisor — a survival-first Kelly Criterion decision skill

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg) ![Claude Skill](https://img.shields.io/badge/Claude-Skill-8A2BE2.svg) ![Version](https://img.shields.io/badge/version-0.1.2-blue.svg) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

> A [Claude](https://claude.ai) skill that turns the Kelly Criterion into a partner
> that makes you think clearly, protects you from ruin, and — when it should —
> **refuses to answer**.
>
> **Survive first. Compound later.**

**Author:** **Hao (駱君昊)** · [@Hao0321](https://github.com/Hao0321) · @Hao0321_Stuido · AIGC / 3D / VFX creator

> 🌐 **中文讀者** → **[看中文版 (README.md)](README.md)**

---

## Start with an experiment

In 2016, Haghani & Dewey gave 61 **finance-trained** people real money and let them
bet on a coin they were **told in advance lands heads 60% of the time**. A huge,
known, in-your-favor edge. The result?

- About **28% went broke** (down to $0)
- Only about **21%** hit the maximum payout
- A number of them even bet on **tails** at some point

**Give people a known, massive edge, and most smart people still lose it all.**
The problem was never the edge. It was the lack of **betting discipline**.

> Source: Haghani & Dewey, *"Rational Decision-Making under Uncertainty: Observed
> Betting Patterns on a Biased Coin"* (2016). Figures are widely-cited values;
> cite the original paper for precision.

The Kelly Criterion is the math of that "correct proportion." This skill helps you
**actually use it** — and use it the right way.

---

## How it's different from a generic Kelly calculator

A normal Kelly calculator takes your `p` and odds and spits out a number. The problems:

1. **The true probability of a life decision is unknowable** → you plug in a guess →
   it returns a number that *looks* scientific but is a guess in disguise. That's
   false precision, and it's dangerous.
2. **Kelly is aggressive** → full Kelly has brutal drawdowns; one overestimate of
   your edge and you slide toward ruin.
3. **Not every decision should use Kelly** → for one-shot, irreversible decisions
   (career change, going all-in), forcing the formula is using a hammer on a screw.

This skill is built **survival-first** to plug all three holes.

---

## Three modes (classify first, then decide whether Kelly even applies)

| Decision type | Examples | Mode |
|---|---|---|
| **Repeatable bet** | investment sizing, ad spend, poker | **Mode 1 · Size** — compute a fractional Kelly position |
| **Allocation** | split limited time/capital across opportunities | **Mode 2 · Allocate** — distribute across bets, cap any single one |
| **One-shot / irreversible** | career change, all-in on a startup, relocating | **Mode 3 · Survive** — **refuses to give a number** → ruin-check + route to a qualitative panel |

> Mode 3 is the most important part. **A tool's dignity is knowing when to say "I shouldn't answer this."**

---

## What it actually looks like

**Example 1 — it sizes your bet (Mode 1)**

> **You:** I have a repeatable strategy, I estimate 60% win rate, 1:1 payoff. How big a position?
>
> **kelly-advisor:**
> [Class] Mode 1 (repeatable bet)
> [Ruin check] capital is risk money you can afford to zero ✅
> [Full Kelly] f\* = 0.6 − 0.4/1 = **0.20**
> [Suggested] ½ × 0.20 = **~10%** ← use this
> [Stress test] if your win rate is really 52% → f\* drops to 0.04 (5× smaller)
> [Insight] "60% means bet 10%, not all-in. And how sure are you about 60%? Less sure → bet less."

**Example 2 — it refuses (Mode 3, the hero feature)**

> **You:** I'm torn on quitting my job to start a company. Use Kelly to tell me if it's worth it.
>
> **kelly-advisor:**
> [Class] Mode 3 → **refuses to use Kelly**
> [Why] This is sample-size-1, irreversible, the probability is unknowable, and half
> the value is non-monetary. Forcing a `p` into the formula dresses up a guess as math
> and makes you overconfident.
> [Reframe instead] How long is your runway? Worst case, do you survive? Is there a
> non-all-in version (part-time bridge, keep an exit)?
> [Route] "Is it worth it" goes to a qualitative panel, not a formula.
> [Insight] "Kelly refuses to answer this — and that refusal is how it helps you."

**A generic Kelly calculator gives you a number in Example 2. This one won't. That's the difference.**

---

## Core discipline

- **Downside first** — confirm the worst case won't take you out *before* looking at upside. Ruin risk → bet → 0.
- **Always fractional** — defaults to ½ Kelly or lower (half-Kelly ≈ 75% of the growth, ~50% of the volatility). Because you *will* overestimate yourself.
- **Bet only surplus** — survival capital always has a Kelly fraction of 0.
- **Honest** — no stock tips, no recommended assets, no guaranteed returns. It helps you **lose survivably and last longer**, not make more.

---

## Install (Claude Code)

```bash
# Put it under ~/.claude/skills/
# Verify the path: ~/.claude/skills/kelly-advisor/SKILL.md
```

Claude.ai: zip the `kelly-advisor/` folder, then Settings → Skills → Upload.

Once installed, just describe any "could-win-could-lose" decision, or say things like
"use Kelly to size this position" / "is this worth going all-in on?" (it'll classify
that as Mode 3 and refuse to gamble, helping you avoid ruin instead).

---

## Structure

```
kelly-advisor/
├── SKILL.md                          # main rules + 3-mode routing + R1–R8
├── CHANGELOG.md
└── references/
    ├── kelly-math.md                 # formulas / fractional Kelly / ruin math / the famous experiment
    └── decision-protocol.md          # 7-step flow + classification tree + 5 worked examples + anti-examples
```

---

## Companion skill

- **[genius-advisor](https://github.com/Hao0321)** — a 9-thinker roundtable (Musk / Jobs /
  Buffett / Munger / Naval / Kiyosaki / MrBeast / Belfort / Trump) for the **qualitative**
  "should I do this?" call. kelly-advisor handles the **quantitative** "how much?" Use both together.

---

## ⚠️ Disclaimer

This skill is a **decision-discipline tool, not investment advice**. No stock tips, no
recommended assets, no guaranteed returns. All probabilities and odds are your own
estimates; output is for thinking only. Real money decisions are at your own risk.

## License

MIT — keep the author attribution (Hao / 駱君昊) and you're free to modify, use, and sell. Fork & PR welcome.

**Find it useful? Drop a ⭐ Star** — and open an issue to share your use case or request a feature.
