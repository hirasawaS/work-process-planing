# AI Work Brain Architecture

## 1. Cognitive model

The system models work as a continuous cognitive loop:

```
Perception
→ Context
→ State
→ Interpretation
→ Reasoning
→ Planning
→ Execution
→ Review
→ Learning
```

### Perception

Receives events from:

- Slack
- meetings/transcripts
- documents
- task systems
- GitHub
- email
- other connected systems

Perception records what happened without prematurely deciding what it means.

### Context

Reads the existing Project Context and related source material.

Context answers:

> What do we know about this project?

It includes durable facts, requirements, design, stakeholders, milestones, and explicit decisions.

### State

Maintains the current working state:

- current phase
- active work
- waiting items
- blockers
- risks
- open loops
- recent changes
- pending questions
- next actions

State answers:

> What is happening now?

### Interpretation

Converts events into meaning.

Examples:

- likely intent of a Slack message
- reason a meeting was called
- implicit expectation
- potential change in assumptions
- stakeholder concern

Interpretation must explicitly distinguish:

```
FACT
INFERENCE
UNKNOWN
```

### Reasoning

Connects the current state to goals and constraints.

Typical reasoning:

```
Issue
→ Cause
→ Impact
→ Options
→ Recommendation
```

### Planning

Turns gaps into executable work.

```
Goal
→ Milestone
→ Deliverable
→ Task
→ Next Action
```

Planning should identify dependencies, owners, deadlines, and critical-path implications where known.

### Execution

Produces drafts or performs approved actions.

Examples:

- Slack reply
- meeting minutes
- agenda
- WBS update
- requirements update
- status report
- research
- Jira/Notion update

Drafting and external side effects must remain separate.

### Review

Checks:

- context consistency
- missing assumptions
- unsupported claims
- stakeholder omissions
- dependency omissions
- critical-path omissions
- output quality
- communication risk

### Learning

Turns human feedback into reusable patterns.

Learning must distinguish:

- one-off correction
- project-specific rule
- reusable personal working rule

## 2. Orchestrator

The Brain Orchestrator coordinates the cognitive modules.

It should:

1. classify incoming events
2. retrieve relevant context
3. reconstruct current state
4. invoke reasoning when interpretation is needed
5. invoke planning when action is needed
6. invoke execution for drafts/actions
7. invoke review before delivery
8. record human feedback
9. trigger learning when a pattern is generalizable

The orchestrator should delegate rather than duplicate every specialist's reasoning.

## 3. Data flow

```
                  Project Context
                       │
                       ▼
Slack ────────→ Perception ────→ State
MTG ──────────→     │              │
Docs ─────────→     │              │
                    ▼              ▼
               Interpretation → Reasoning
                                   │
                                   ▼
                               Planning
                                   │
                                   ▼
                               Execution
                                   │
                                   ▼
                                Review
                                   │
                         ┌─────────┴─────────┐
                         ▼                   ▼
                    Human review        External action
                         │
                         ▼
                      Feedback
                         │
                         ▼
                      Learning
                         │
                         └──────→ Future runs
```

## 4. Safety boundary

AI may infer and draft aggressively, but it must not silently turn an inference into a fact or execute consequential external actions without the required approval.
