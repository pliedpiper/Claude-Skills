# Spec Drafter Skill

Deep-dive interview process to transform rough ideas into comprehensive technical specifications.

## Trigger

User mentions a SPEC.md file or asks to write/refine a specification.

## Workflow

### Step 1: Read Existing Spec

Read the referenced SPEC.md (or similar spec file) to understand:
- The core idea/feature
- Any existing requirements
- Current level of detail
- Gaps and ambiguities

If no file exists, ask the user to describe what they want to build.

---

### Step 2: Conduct Deep-Dive Interview

Use the `AskUserQuestion` tool to interview the user **continuously** until the spec is complete.

**Interview Rules:**
- Ask 1-4 questions per round (use the tool's multi-question capability)
- **Avoid obvious questions** - don't ask things that are self-evident from the spec
- **Go deep** - probe edge cases, failure modes, and implicit assumptions
- **Be specific** - reference concrete scenarios, not abstract concepts
- Continue interviewing until all major areas are covered

**Question Categories (cycle through these):**

#### Technical Implementation
- Data model decisions and tradeoffs
- API design choices (REST vs GraphQL, sync vs async)
- State management approach
- Authentication/authorization model
- Caching strategy and invalidation
- Database schema implications
- Third-party service dependencies
- Error handling philosophy
- Performance requirements and bottlenecks
- Concurrency and race condition handling

#### Architecture & Scale
- Expected load and growth patterns
- Horizontal vs vertical scaling approach
- Microservices vs monolith considerations
- Event-driven vs request-response patterns
- Data consistency requirements (eventual vs strong)
- Backup and disaster recovery needs

#### UI/UX (if applicable)
- User mental model assumptions
- Loading and empty states
- Error presentation to users
- Accessibility requirements
- Mobile vs desktop priorities
- Offline behavior expectations
- Animation and transition preferences
- Information hierarchy decisions

#### Edge Cases & Failure Modes
- What happens when X fails?
- How do users recover from Y?
- What if data is partially corrupted?
- Handling of concurrent edits
- Network interruption behavior
- Graceful degradation strategy

#### Business & Product
- Priority of features (MVP vs future)
- Success metrics and how to measure them
- Compliance or regulatory constraints
- Internationalization requirements
- Rollout strategy (feature flags, gradual release)
- Rollback plan if something goes wrong

#### Security & Privacy
- Sensitive data handling
- Audit logging requirements
- Rate limiting approach
- Input validation boundaries
- Session management
- Data retention policies

#### Integration & Compatibility
- Backward compatibility requirements
- Migration path from existing systems
- API versioning strategy
- Third-party integration constraints
- Browser/platform support matrix

---

### Step 3: Synthesize Responses

After each interview round:
1. Mentally track what's been covered
2. Identify remaining gaps
3. Formulate next round of questions that build on previous answers
4. Stop when you have enough detail to write a comprehensive spec

**Completion Criteria:**
- Core functionality is fully defined
- Major edge cases are addressed
- Technical approach is clear
- Success criteria are established
- Open questions are documented (if any remain)

---

### Step 4: Write the Spec

Write the complete specification to the SPEC.md file (or specified file) with this structure:

```markdown
# [Feature/Project Name]

## Overview
[2-3 sentence summary of what this is and why it matters]

## Goals
- [Primary goal]
- [Secondary goals]

## Non-Goals
- [Explicitly out of scope items]

## Technical Design

### Data Model
[Schema, relationships, key entities]

### API Design
[Endpoints, request/response shapes, authentication]

### Architecture
[System components, data flow, dependencies]

## User Experience

### User Flows
[Step-by-step flows for key actions]

### States & Edge Cases
[Loading, empty, error, offline states]

## Security Considerations
[Auth, data protection, validation]

## Performance Requirements
[Latency targets, throughput, caching]

## Implementation Plan
[Phases, dependencies, rough ordering]

## Open Questions
[Unresolved items for future discussion]

## Success Metrics
[How we know this worked]
```

Adapt the structure based on what's relevant - skip sections that don't apply.

---

## Example Interview Flow

**Round 1:** High-level architecture and data model
**Round 2:** API design and state management
**Round 3:** Edge cases and error handling
**Round 4:** Security and performance
**Round 5:** UX details and rollout strategy
**Round 6:** Final clarifications and open questions

Adjust based on complexity - simple features may need 2-3 rounds, complex systems may need 8+.

---

## Notes

- Don't rush - a thorough spec saves implementation time
- Challenge assumptions - ask "why" when something seems arbitrary
- Document tradeoffs - capture rejected alternatives and reasoning
- Be opinionated - suggest approaches when the user is unsure
- Flag risks - proactively identify potential issues
