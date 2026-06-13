---
title: "What's an AI Agent? And Why Is that Hard to Define? (The Agents Season, Episode 1)"
podcast: "Linear Digressions"
hosts: "Katie Malone & Ben Jaffe"
source: "https://soundcloud.com/linear-digressions/whats-an-ai-agent-and-whys"
published: 2026-04-19
captured: 2026-06-13
---

# What's an AI Agent? And Why Is that Hard to Define?

> "AI agent" resists a clean definition not because the field is sloppy, but
> because it's a **spectrum, not a category**. The useful test isn't "does it call
> a tool?" — a single tool call is just a responder with extra steps. It's whether
> the system runs a loop: **perceive → reason → act → observe → repeat, until a
> goal is met.** And the moment that loop touches the real world, the hard question
> stops being technical and becomes: *what happens when it's wrong, and who catches
> it?*

## Core message

The season opener refuses to hand over a one-line definition, because the honest
answer is that "agent" spans a range of autonomy. The marketing noise is real, but
underneath it sits a genuine conceptual problem: agency is graded, consequences
escalate as the loop gets more autonomous, and accountability has no clean answers
yet. The episode's job is to install the **observe–reason–act loop** as the mental
model for the whole season.

## The working definition

> "an AI that perceives its environment, reasons about what to do next, acts, and
> then repeats that cycle until a goal is met"

Drawn from the **ReAct** framing (the subject of Episode 2). The load-bearing word
is *repeats*: the loop, not the tool call, is what makes something an agent.

## The key distinction: a loop, not a tool call

- **One tool call + a reply** = "basically a responder with extra steps." Tool
  access alone does **not** make an agent.
- The dividing line is whether the system **observes the result and adjusts** —
  whether the output of an action feeds back into the next decision.
- "Agentic" is a claim about **control flow**, not about having plugins.

## Consequences are the real frontier

The stakes change qualitatively once actions **persist beyond the conversation**:
- A wrong chatbot answer is annoying and ends with the message.
- A wrong *agent* — one that books the wrong flight, sends the email, commits you
  to a meeting — creates durable, real-world harm and an accountability gap that
  "doesn't have clean answers yet."
- Delegation isn't binary handoff. In practice you **segment a task**: delegate
  some steps, keep others, and live with an ambiguous middle.

## Several legitimate definitions, different emphases

There is no single canonical definition; communities foreground what they care
about:
- **Russell & Norvig** (the classic AI textbook): perception of, and action on, an
  environment.
- **Anthropic**: the weight of **real-world consequences**.
- **ReAct paper**: the **reasoning loop** itself.

These aren't contradictions — they're three angles on the same graded thing.

## Practical takeaways

- **Apply the loop test before believing the label.** "Agentic" is only earned if
  the system actually runs perceive→reason→act→**observe**→repeat. If output never
  feeds back into the next step, it's a responder with extra steps.
- **Understand agency as a dial, not a switch.** Decide *how much* you're
  delegating per sub-task, not whether the whole thing is "an agent."
- **Lead with the failure question.** For anything that acts in the world, the
  decision-relevant question isn't "what can it do?" but "**what happens when it
  makes a mistake, and who catches it?**" Build the review path before granting the
  permissions.
- **Distrust the marketing use of "agent."** Treat it as a spectrum claim and ask
  where on the autonomy/consequence axis a given system actually sits.

## Next in the season

Episode 2 traces *how* the loop became possible: the two 2022–2023 papers — ReAct
and Toolformer — that let models interleave reasoning with action and decide for
themselves when to reach for a tool.
