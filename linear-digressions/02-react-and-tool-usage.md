---
title: "ReAct and Tool Usage (The Agents Season, Episode 2)"
podcast: "Linear Digressions"
hosts: "Katie Malone & Ben Jaffe"
source: "https://soundcloud.com/linear-digressions/react-and-tool-usage-the"
published: 2026-04-26
captured: 2026-06-13
---

# ReAct and Tool Usage

> Before late 2022 there was a wall between AI and the world: models could reason
> beautifully but couldn't look anything up, run code, or check whether what they
> said was true. Two papers tore the wall down. **ReAct** showed what happens when
> you interleave reasoning and action in a loop; **Toolformer** taught a model to
> decide *for itself* when to reach for a tool. Reasoning without action stays
> stuck in its own head; action without reasoning is brittle and aimless. Put them
> together and you get the architecture every modern agent runs on.

## Core message

The leap to agents wasn't a bigger model — it was **grounding**. Once a model can
take an action, observe the result, and fold that observation back into its next
thought, it stops fabricating and starts verifying. The episode tells this as two
complementary breakthroughs: ReAct solved the **architecture** problem (how to
weave reasoning and acting together), Toolformer solved the **decision** problem
(how a model learns *when* a tool is worth calling).

## Paper 1 — ReAct (Yao et al., 2022; ICLR 2023)

- The pattern: **Think → Act → Observe → repeat.** Reasoning steps and tool
  actions are interleaved in one loop instead of separated.
- The result: this cycle **significantly outperformed both chain-of-thought-only
  and action-only** approaches on multi-hop question answering — because the model
  could **ground its reasoning in retrieved facts** rather than confabulate.
- This is the exact loop Episode 1 used to *define* an agent. ReAct is where the
  definition comes from.

## Paper 2 — Toolformer (Schick et al., Meta AI, 2023)

- The insight: a model can **learn *when* to use a tool, not just how.**
- The method: self-supervised — train on examples where inserting an API call
  **actually improved the next-token prediction**, so the model internalizes the
  judgment of when a tool earns its cost.
- The result: a **relatively small fine-tuned model with tool access could compete
  with much larger models.** Tools substitute for raw scale.

## Why both, not either

> "Reasoning without action leaves a model stuck in its own head, and action
> without reasoning leads to brittle, aimless tool use."

ReAct = the loop; Toolformer = the trigger. Modern agents need both: a structure
that integrates acting with thinking, *and* learned discretion about when acting
is worth it.

## From papers to infrastructure

- **Model Context Protocol (MCP)** — Anthropic, late 2024. A **standard** for
  connecting tools to models, replacing bespoke per-integration glue. Adopted even
  by competitors (OpenAI, Google DeepMind) — a rare cross-vendor standard.
- **OpenClaw** — the open-source agent project that went **0 → ~250,000 GitHub
  stars**. Bundles instructions for specific tools into a **"skills"** system; a
  direct, consumer-facing implementation of the ReAct + Toolformer ideas. The
  speed of that adoption signals large **latent demand for delegated agency**.

## Practical takeaways

- **Look for the grounding step.** When judging an AI tool, check whether it can
  actually **search/retrieve** and feed that back in. Grounding is what separates a
  verified answer from a confident guess.
- **Separate the two concerns when you build.** Keep the **reasoning loop** distinct
  from **tool selection**, and add diagnostics that test whether a tool call
  *improved* the output — don't just count that calls happened.
- **Before granting real-world permissions, ask three things:** what tools does it
  access, what happens on a wrong action, and who reviews the action history?
  Persistent tool access + autonomous decisions is **qualitatively** different from
  a chatbot.

## Next in the season

Episode 3 — **Lost in the Middle** — turns to a structural weakness of the very
context window all this reasoning lives in: information buried in the middle gets
ignored, which is why *where* you put information matters as much as whether it's
present.
