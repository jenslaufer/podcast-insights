# It's Just Math

An interactive, single-file web essay on **convexity, compounding, and non-ergodicity** — built as a gift for David Dredge (Convex Strategies) and anyone who thinks in geometric returns (Ole Peters, Nassim Taleb).

One self-contained `index.html`. No build step, no dependencies, runs offline. Open it or host it anywhere (e.g. GitHub Pages) and share the link.

## What it shows

Three interactive games, each with a depth switch — **Intuition → The Mathematics → The Proof**:

1. **Non-ergodicity** — Ole Peters' multiplicative coin toss (×1.5 / ×0.6). The ensemble grows +5%/round while every single path decays −5.13%/round. Play one trajectory, then run a 1,000-player casino and watch the median go broke while the luckiest 1% hoards the wealth.
2. **The volatility tax** — same arithmetic mean, more variance, less money kept. `geometric ≈ arithmetic − σ²/2`. Slider holds the average at +5% and widens the swings.
3. **Convexity** — Dredge's / Spitznagel's core claim: a crash hedge that loses 20%/yr standalone, allocated at x*=4%, lifts compound growth 14.06% → 15.23% while *lowering* the arithmetic mean 17.5% → 16.0% — ending with 2.79× the wealth over 100 periods. Advanced controls let you move the payoff multiple and crash probability and watch the optimum appear and vanish.

## Accuracy

Every number is exact and reproducible. The math follows Ole Peters, *"The ergodicity problem in economics,"* Nature Physics 15 (2019); the volatility-tax framing follows Spitznagel, *Safe Haven* (2021). Charts compute `g = E[ln(1+r)]` directly rather than leaning on the `σ²/2` shorthand, so large-move cases stay correct.

## Before sharing

- Replace the footer link (`<!-- TODO Jens -->`) with your "what I'm working on" page.
- Optionally host on GitHub Pages and send the link with `cover-note.md`.
