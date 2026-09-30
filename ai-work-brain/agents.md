# Agent Contracts

## Brain Orchestrator

### Responsibility
Coordinate the work loop and delegate to specialist agents.

### Inputs
- event
- project context
- current state
- prior decisions
- open loops

### Outputs
- updated state proposal
- reasoning requests
- planning requests
- execution requests
- review requests
- human approval requests

### Rule
Do not invent missing project facts.

---

## Context Agent

### Responsibility
Reconstruct relevant durable context and current state.

### Outputs
- relevant context
- current phase
- current state
- affected milestones
- affected decisions
- related open loops

### Rule
Prefer source-backed facts. Mark uncertainty explicitly.

---

## Reasoning Agent

### Responsibility
Interpret messages, meetings, and changes.

### Outputs
- literal request
- likely intent
- background hypotheses
- stakeholder expectations
- implications
- risks
- questions
- confidence

### Required classification

```
FACT
INFERENCE
UNKNOWN
```

### Example

Input:

> 「○○の件、その後どうなっていますか？」

Output:

- FACT: sender asked for status of ○○.
- INFERENCE: sender may need progress visibility before an upcoming review.
- UNKNOWN: whether the sender is concerned about delay.
- Suggested next action: verify current status and reply with current state + next milestone.

---

## Planning Agent

### Responsibility
Discover and structure the work required to move the project forward.

### Outputs
- goal
- deliverables
- tasks
- dependencies
- critical path
- owner
- deadline
- next action

### Rule
Do not create detailed WBS merely because detailed WBS is possible. Match task granularity to the actual work process.

---

## Execution Agent

### Responsibility
Create useful work products.

### Examples
- Slack drafts
- meeting minutes
- agendas
- requirements drafts
- reports
- research
- WBS updates

### Rule
Drafting is not the same as sending or committing an external change.

---

## Review Agent

### Responsibility
Challenge the output before delivery.

### Review dimensions
1. correctness
2. context consistency
3. assumptions
4. missing dependencies
5. stakeholder impact
6. clarity
7. actionability
8. unsupported inference
9. deadline impact
10. alignment with prior decisions

---

## Feedback Agent

### Responsibility
Turn human criticism into structured learning signals.

### Inputs
- original output
- human correction
- revised output
- surrounding context

### Outputs
- feedback category
- root cause
- correction
- generalized lesson
- confidence
- scope

Possible categories:

- context miss
- intent miss
- assumption miss
- reasoning error
- planning error
- granularity error
- communication error
- missing stakeholder
- missing dependency
- process mismatch
- factual error
- unnecessary complexity
- style preference

### Critical distinction

Every feedback item must be classified as one of:

```
ONE_OFF_CORRECTION
PROJECT_RULE
REUSABLE_WORKING_RULE
```

Do not turn every correction into a permanent personal rule.

---

## Learning Agent

### Responsibility
Promote high-quality feedback into reusable memory.

A lesson should be promoted only when:

- it is explicitly confirmed by the user, or
- the same pattern is observed repeatedly with sufficient confidence.

Learning must preserve provenance:

- source feedback
- date
- scope
- confidence
- affected agent
