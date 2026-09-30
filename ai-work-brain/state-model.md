# Work Brain State Model

## Current State

```yaml
phase:
objective:
current_status:
active_work:
recent_changes: []
milestones: []
open_loops: []
waiting: []
blockers: []
risks: []
assumptions: []
questions: []
decisions: []
next_actions: []
```

## Open Loop

An open loop is an unresolved commitment, question, dependency, or expected follow-up.

```yaml
id:
description:
source:
owner:
status: open | waiting | blocked | resolved
due:
dependency:
last_update:
next_action:
```

The system must check whether every new event affects an existing open loop.

## Event

```yaml
id:
timestamp:
source: slack | meeting | document | task | other
participants: []
topic:
facts: []
inferences: []
unknowns: []
decisions: []
questions: []
actions: []
related_context: []
affected_open_loops: []
```

## Decision

Decisions are explicit commitments, not inferred preferences.

```yaml
id:
decision:
date:
decided_by: []
rationale:
source:
supersedes:
status: active | superseded
```

## Assumption

Assumptions must be explicit because they are common sources of planning failure.

```yaml
id:
statement:
source:
confidence:
validation_method:
status: active | validated | rejected
```

## State update rules

1. Facts from trusted sources may update state directly.
2. Inferences may propose state changes but should not silently become facts.
3. Explicit decisions may update state and planning.
4. New events must be checked against open loops.
5. Material state changes should be traceable to their source.
6. When an assumption is rejected, dependent plans should be reconsidered.
