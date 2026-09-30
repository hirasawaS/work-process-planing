# Human Feedback Learning Loop

Human review is not merely quality control. It is a learning signal.

## Flow

```
AI Output
↓
Human Review
↓
Correction
↓
Feedback Agent
↓
Root Cause
↓
Generalization
↓
Learning Memory
↓
Future Agent Behavior
```

## Example

### AI output

> Create a WBS with one work item per use case.

### Human feedback

> 「今回はユースケース単位でFIXするプロセスじゃない。説明・確認しながら一つの要件定義書にまとめて最後にFIXする前提。」

### Feedback extraction

```
Category:
process mismatch

Root cause:
The agent assumed a use-case-oriented requirement finalization process.

Correction:
WBS should reflect the actual document finalization process.

Scope:
project-specific

Generalizable lesson:
Before creating a WBS, identify how the deliverable is actually reviewed, updated, and finalized.

Classification:
REUSABLE_WORKING_RULE
```

## Learning levels

### Level 1: One-off correction

Only affects the current output.

Example:

> Change this sentence.

Do not create a permanent rule.

### Level 2: Project rule

Applies to the current project.

Example:

> This project finalizes requirements through a single document after iterative explanation/review.

Store in project-scoped learning.

### Level 3: Reusable working rule

Applies across projects.

Example:

> Before decomposing a requirements document into a WBS, confirm the actual review/finalization process.

Promote only when explicitly confirmed or repeatedly observed.

## Personal Operating Model

Over time, reusable feedback can form a compact working model:

- communication preferences
- preferred output granularity
- planning style
- review expectations
- recurring blind spots
- preferred decision format

The model should remain editable, explainable, and traceable to feedback.

## Anti-patterns

Do not:

- memorize every correction as a global rule
- infer personality from one correction
- overwrite explicit project context with a guess
- treat AI-generated inference as human feedback
- hide why a rule was learned
