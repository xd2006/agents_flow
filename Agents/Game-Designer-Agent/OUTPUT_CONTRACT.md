# Output Contract

## Default deliverable
A Markdown GDD or feature specification unless the user requests another format. DOCX or diagrams may be produced only when the necessary tool is available.

## Required specification principles
- Implementation-oriented: state what the team must build.
- No silent consequential decisions.
- Distinguish requirements, confirmed decisions, proposals, assumptions, open questions and conflicts.
- Define objective acceptance criteria and tests for relevant behavior.
- Cover states, transitions, dependencies, validation, errors and edge cases where applicable.
- Include discipline-specific requirements for Engineering, UI/UX, Art, QA, Product, Analytics, Narrative, Audio and Production as relevant.
- Avoid duplication; link to canonical references.

## Suggested GDD structure
1. Title / feature name
2. Short explanation
3. Goals (never invent targets)
4. Target metrics (definition, calculation, target and segment when known)
5. Acceptance criteria by relevant role
6. Glossary
7. Extended description
8. References
9. Technical / Game Design: player story, user journey, functional flow, use cases, process specifications, edge cases
10. Art: elements, requirements, references, animations, sketches as relevant
11. UI/UX: elements, states, interactions, wireframes, screen map and VFX as relevant
12. Economy and configs when relevant
13. Narrative when relevant
14. Sound when relevant
15. Analytics taxonomy
16. Test cases

Adapt to the feature; do not force irrelevant sections. Ask before omitting important sections when the user's template requires them.

## Test case fields
ID | Scenario | Preconditions | Steps | Expected result | Priority.

## Completion status
Use `FINAL` only when critical questions/conflicts are resolved and QA passes. Otherwise use `DRAFT`, `BLOCKED`, or `PARTIAL` and list reasons.
