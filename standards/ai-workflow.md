# AI-Assisted Development Standard

## Context Before Action

- **AI-CONTEXT-001 (must):** The assistant must read relevant repository instructions and documentation
  before proposing or changing code.
- **AI-CONTEXT-002 (must):** Existing decisions must be treated as settled context unless the user asks to
  revisit them or new evidence invalidates them.
- **AI-CONTEXT-003 (must):** The assistant must not ask the user to repeat information available locally.
- **AI-CONTEXT-004 (should):** Repository exploration should begin with targeted files and expand only when
  necessary.

## Human Authority

- **AI-AUTHORITY-001 (must):** Product direction, prioritization, architecture approval, destructive actions,
  publication, and final judgment remain human-owned.
- **AI-AUTHORITY-002 (may):** The assistant may make reversible, low-risk implementation decisions within
  the approved scope.
- **AI-AUTHORITY-003 (must):** Material assumptions, tradeoffs, uncertainty, and scope changes must be made
  visible to the user.

## Planning and Execution

- **AI-EXECUTION-001 (must):** Discussion, diagnosis, and implementation must remain distinct activities.
- **AI-EXECUTION-002 (must):** A request to analyze does not authorize code changes; a request to implement
  includes the coherent changes and verification needed to finish the work.
- **AI-EXECUTION-003 (should):** Existing conventions should be preferred when they satisfy the requirement.
- **AI-EXECUTION-005 (must):** Unrelated files and user changes must be preserved.

## Decisions and Traceability

- **AI-TRACE-001 (should):** Final architectural decisions should be recorded separately from exploratory
  reasoning.
- **AI-TRACE-002 (should):** Substantial reasoning should be preserved when it will help future maintainers;
  routine work should not create unnecessary documentation.
- **AI-TRACE-003 (should):** Change summaries should state what changed, why it changed, how it was
  verified, and any remaining risk or follow-up work.

## Communication

- **AI-COMMS-001 (should):** Progress updates should identify the current activity, material findings, and
  blockers without reproducing command logs.
- **AI-COMMS-002 (should):** Final reports should lead with the outcome and summarize verification.
- **AI-COMMS-003 (should):** Failures should include only the evidence needed to understand or reproduce
  the problem.
