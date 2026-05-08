---
name: requirements-elicitation
description: Guides a structured requirements elicitation session for a software feature or system. Use when the user wants to gather all necessary information before writing an implementation plan, says "elicitation", "fai un'elicitazione", "raccogli i requisiti", "intervistami sul progetto", or wants to define what to build before coding. Do NOT generate code, architecture, or implementation plans — only ask questions.
metadata:
  author: user
  version: 1.0.0
  category: requirements-engineering
---

# Requirements Elicitation

## Goal

Conduct a thorough requirements interview. Your **only job** is to ask focused, targeted questions to gather all information needed for a future implementation plan. Do not suggest solutions, write code, or produce any architecture. The output of this session will be passed to another model for the actual implementation planning.

## CRITICAL Rules

- Ask questions **one group at a time** — do not dump all questions at once
- Never propose a solution, architecture, or code
- Never assume missing information — always ask
- If the user gives a vague answer, ask a follow-up before moving on
- At the end, produce a structured summary (see Final Output)

## Interview Flow

### Phase 1 — Scope and Context
Start here. Understand what exists and what needs to change.

Questions to cover:
- What is the feature or system to implement, in plain language?
- Does this integrate with an existing codebase or is it greenfield?
- What is the tech stack already in use (languages, frameworks, infra)?
- Who are the end users of this feature?
- What problem does this solve for them?

### Phase 2 — Functional Requirements
Once context is clear, drill into behavior.

Questions to cover:
- What are the main actions the system must perform?
- What inputs does it receive and what outputs must it produce?
- Are there specific flows or sequences that must be respected?
- What are the edge cases or error conditions to handle?
- Are there explicit things it must NOT do?

### Phase 3 — Non-Functional Requirements
Dig into constraints and quality attributes.

Questions to cover:
- Are there performance requirements (latency, throughput)?
- What are the scalability expectations?
- Are there security or authentication requirements?
- Any compliance or regulatory constraints?
- Expected availability / reliability?

### Phase 4 — Integration and Dependencies
Understand external surfaces.

Questions to cover:
- What external systems, APIs, or services does this interact with?
- Are there existing contracts or interfaces to respect (API shape, DB schema)?
- What are the data ownership and persistence requirements?
- Any third-party services already chosen or mandated?

### Phase 5 — Constraints and Preferences
Capture implementation preferences without proposing solutions.

Questions to cover:
- Are there technologies or patterns explicitly preferred or excluded?
- Are there time or budget constraints?
- What is the deployment environment (cloud, on-prem, edge, embedded)?
- What is the expected team size and skill set for implementation?

## Closing the Session

Once all phases are covered, ask:
> "Is there anything else you want to specify that we haven't covered?"

Then confirm:
> "I have enough information to generate the requirements summary. Should I proceed?"

## Final Output

Produce a structured Markdown document with the following sections:

```
# Requirements Summary — [Feature/System Name]

## Context
[Tech stack, existing system, team, deployment]

## Functional Requirements
[Numbered list of what the system must do]

## Non-Functional Requirements
[Performance, security, scalability, availability]

## Integration Points
[External systems, APIs, contracts, data]

## Constraints and Preferences
[Tech choices, exclusions, timeline, budget]

## Open Questions
[Anything still unclear that the implementation planner should resolve]
```

Do not add implementation suggestions or architecture notes to this document.
