# AI Work Brain — High-Level Cognitive Architecture

## 0. Purpose

This is not a chatbot architecture.

The target system is a **high-level cognitive work system** that converts vague human intent into an executable work system.

The user should not need to know how to decompose work.

The AI should.

## 1. Cognitive Stack

```
L0 Sensors
  Slack / Meetings / Docs / GitHub / Jira / Notion / Email / Files

L1 Perception
  What happened?

L2 Memory
  What do we know about this project, people, decisions and history?

L3 State
  What is true right now?

L4 Interpretation
  What does the latest information mean?

L5 Problem Framing
  What is the actual problem?

L6 Goal Design
  What outcome should be achieved?

L7 Work Discovery
  What work must exist for that outcome to happen?

L8 Planning
  In what order, with what dependencies and evidence?

L9 Execution
  What can the AI produce or perform now?

L10 Review
  Is the work correct, useful and sufficient?

L11 Learning
  What should the system do differently next time?
```

The system must be able to move up and down this stack dynamically.

## 2. Intent-to-Work Compiler

The core capability is an **Intent-to-Work Compiler**.

Input:

> 「来週までに銀行側と要件を詰めたい」

The system should compile this into:

```
Intent
↓
Outcome
↓
Stakeholder objective
↓
Current state
↓
Gap
↓
Required decisions
↓
Required evidence
↓
Required artifacts
↓
Required coordination
↓
Work packages
↓
Tasks
↓
Next actions
```

The compiler must not blindly decompose the sentence.

It must first determine what work is actually implied.

## 3. Work Discovery

Work Discovery is more important than task decomposition.

The system asks internally:

- What outcome is actually desired?
- What must be true for that outcome to happen?
- What is currently preventing it?
- What evidence is missing?
- Which decisions are unresolved?
- Which stakeholders must act?
- Which artifact enables the next decision?
- Which dependencies are hidden?
- What work has not yet been named?

This prevents the classic failure mode:

> beautifully structured tasks that do not actually move the project.

## 4. Cross-Source Reasoning

The Brain should treat connected sources as one evidence graph.

```
Slack
Meeting
Document
Task
GitHub
Notion
Email
       ↓
Evidence Graph
       ↓
Project State
```

A single source should not be treated as the entire truth.

Example:

A Slack message says:

> 「来週までにお願いします」

The Brain should retrieve related context and determine:

- what "it" refers to
- what "done" means
- who requested it
- why next week matters
- whether a prior decision exists
- whether a dependency blocks it
- whether a milestone is affected

Only then should it create work.

## 5. Project State as a Dynamic Model

The Brain continuously maintains:

```Objective
Current Phase
Milestones
Decisions
Assumptions
Open Questions
Open Loops
Dependencies
Risks
Stakeholders
Workstreams
Artifacts
Pending Actions
Recent Changes
```

Every important incoming event should answer:

> Did the state change?

If yes:

1. identify the changed state
2. identify impacted work
3. identify newly required work
4. re-plan where necessary

## 6. Planning Engine

Planning is not a static WBS generator.

It is a dynamic optimization process.

```
Current State
+
Desired Outcome
+
Constraints
+
Dependencies
+
Uncertainty
↓
Candidate Work Plans
↓
Plan Critique
↓
Selected Work Plan
```

The planner should optimize for:

- outcome impact
- critical-path speed
- information gain
- dependency reduction
- stakeholder coordination cost
- rework risk
- execution feasibility

Do not optimize for the number of tasks or visual completeness.

## 7. Information-Gain Strategy

When uncertainty is high, the Brain should prefer actions that reduce uncertainty quickly.

For example:

```
Unknown AS-IS
↓
Do not create 30 downstream tasks
↓
Create the smallest evidence-gathering action
↓
Update state
↓
Re-plan
```

This is critical for dynamic consulting work.

## 8. Deliverable-First Planning

The Brain should reason backward from required outcomes.

```
Desired Decision
↓
Information required
↓
Analysis required
↓
Artifacts required
↓
Work required
↓
Coordination required
```

This is preferable to starting with:

> 「とりあえずタスクを洗い出す」

## 9. Stakeholder Coordination Minimization

Human coordination is expensive.

The system should therefore minimize unnecessary human interaction.

Before asking the user to contact someone, the Brain should attempt to:

1. search existing information
2. infer the current state
3. identify whether the question is actually unresolved
4. determine the minimum information needed
5. draft the exact communication
6. explain why the communication is required

The ideal output is:

> 「Aさんにこれだけ確認してください」

not:

> 「関係者と調整してください」

## 10. Executive Brief

The Brain should maintain a concise executive layer.

Every project should be compressible into:

```
Goal
Current State
What's Changed
What's Blocking
Critical Path
Top Risks
Decisions Needed
Next 3 Actions
```

This allows the user to regain project context without rereading everything.

## 11. Autonomous Research

When the Brain lacks information, it should distinguish:

- information already available
- information available through connected sources
- information requiring external research
- information only a human can provide

The AI should research available information before asking the user.

## 12. Self-Critique

Before delivering an important output, the Brain should run an adversarial review:

- What assumption could be wrong?
- What important context was missed?
- What would the stakeholder object to?
- What dependency is invisible?
- What evidence is weak?
- What happens if this plan fails?
- Is there a simpler route?
- Are we solving the actual problem?

## 13. Learning Architecture

Learning occurs at three levels.

### Episodic

What happened in this project?

### Semantic

What is generally true about this project/domain?

### Procedural

How should the user and AI work together?

Procedural learning is the most important long-term layer.

Example:

```
Human:
「その粒度じゃなくて、先にAS-IS確認」

↓
Feedback extraction

↓
Rule candidate:
「When requirements depend on existing implementation,
verify AS-IS before decomposition.»

↓
Repeated confirmation

↓
Reusable procedural memory
```

## 14. Memory Governance

Every learned rule has:

```
Rule
Scope
Source
Confidence
Created
Last Confirmed
Evidence Count
Status
```

Possible scope:

- task
- project
- domain
- personal working style
- global

This prevents accidental over-generalization.

## 15. Orchestrator

The Orchestrator decides which cognitive capability to invoke.

Pseudo-flow:

```
receive(input)

→ classify_intent()

→ retrieve_context()

→ reconstruct_state()

→ detect_missing_information()

→ research_if_possible()

→ frame_problem()

→ define_outcome()

→ discover_work()

→ generate_plan()

→ critique_plan()

→ execute_safe_actions()

→ generate_deliverables()

→ review()

→ request_human_approval_if_needed()

→ capture_feedback()

→ update_memory()

→ update_state()

→ repeat
```

The Orchestrator should continue until one of these conditions is reached:

1. desired outcome is achieved
2. human decision is required
3. human coordination is required
4. external permission is required
5. information cannot be obtained automatically
6. risk exceeds the allowed autonomy boundary

## 16. Autonomy Levels

### L0 — Answer

AI only responds.

### L1 — Recommend

AI proposes next actions.

### L2 — Design

AI creates the complete work plan.

### L3 — Produce

AI creates artifacts and drafts.

### L4 — Execute

AI performs permitted tool actions.

### L5 — Operate

AI continuously monitors state and proactively discovers and executes work within defined boundaries.

The target architecture is L4-L5 for low-risk work, while consequential decisions and human-to-human commitments remain human-controlled.

## 17. Success Metric

The system should not be evaluated by:

- how intelligent its explanations sound
- how many tasks it creates
- how much text it generates

Evaluate it by:

```
How much cognitive work was removed from the human
while preserving decision quality?
```

The ideal user experience is:

> 「俺は最低限、人と調整する。あとはAIが仕事を設計して進める。」
