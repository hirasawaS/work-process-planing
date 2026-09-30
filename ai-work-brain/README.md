# AI Work Brain

AI Work Brain is the cognitive layer of Personal Work OS.

The existing repository already provides a framework for defining work, planning, execution, review, and update. AI Work Brain extends that framework from **task assistance** toward **continuous work execution**.

## Core idea

```
Project Context = Long-term memory / SSOT
Work Brain      = Working memory + state + reasoning + planning
Agents          = Specialized execution capabilities
Human           = Decision maker / approver
```

The target loop is:

```
Slack / MTG / Docs / Tools
        ↓
     Perception
        ↓
Context + Current State
        ↓
Interpretation
        ↓
Reasoning
        ↓
Planning
        ↓
Execution
        ↓
Review
        ↓
Human Feedback
        ↓
Learning
        ↓
Updated State / Better Future Output
```

The goal is not to make an AI that answers questions well. The goal is to make an AI that can **understand the current work state, discover what work is needed, perform that work, and improve from human review**.

## Why this exists

Dynamic knowledge work requires more than reading and writing documents. It requires continuously reconstructing:

- what the project is trying to achieve
- what is currently true
- what changed
- why someone sent a message
- what people implicitly expect
- what remains unresolved
- what should happen next
- which output should be produced
- whether the output is actually appropriate

Project Context stores the durable facts and decisions. Work Brain turns those facts and incoming events into action.

## Design principles

1. **Context and Brain are separate.**
2. **Fact and inference are separate.**
3. **State is first-class.**
4. **Tasks are derived from state and gaps, not managed in isolation.**
5. **Task discovery is part of AI responsibility.**
6. **External actions are separated from drafting and require human approval where appropriate.**
7. **Human feedback is a first-class learning signal.**
8. **One-off corrections must be distinguished from reusable rules.**
9. **AI must never silently convert uncertainty into fact.**
10. **The system optimizes for moving work forward, not preserving an outdated plan.**

## Human feedback loop

The system is intentionally designed for repeated review:

```
AI output
  ↓
Human review
  ↓
Correction / criticism
  ↓
Feedback classification
  ↓
Generalizable lesson?
  ↓ yes
Learning memory
  ↓
Future reasoning / planning / execution
```

The AI should learn the user's **work patterns**, not blindly memorize every individual correction.

## Initial scope

The MVP focuses on:

- Slack/message interpretation
- Meeting interpretation
- current-state reconstruction
- open-loop management
- next-action discovery
- output drafting
- human review
- feedback capture
- reusable learning

External write actions and fully autonomous execution can be added later.
