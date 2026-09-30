# Slack Event Workflow

## Goal

Convert a Slack message into an actionable work event.

## Flow

```
Slack message
↓
Context retrieval
↓
Literal request
↓
Intent hypothesis
↓
Affected state
↓
Open-loop impact
↓
Next action
↓
Reply draft
↓
Review
↓
Human approval
```

## Required output

### 1. Literal request
What does the sender explicitly ask?

### 2. Background hypothesis
Why might they be asking now?

### 3. Expected action
What is the sender likely expecting?

### 4. Related context
Which project facts, decisions, milestones, or prior conversations matter?

### 5. State impact
Did the message change the current state?

### 6. Open-loop impact
Does it create, update, or resolve an open loop?

### 7. Recommended response
Draft a response appropriate to the confidence level.

Never present an intent hypothesis as a fact.
