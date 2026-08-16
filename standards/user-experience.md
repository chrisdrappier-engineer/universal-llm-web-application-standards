# User Experience Standard

## Clarity and Consistency

- **UX-CLARITY-001 (should):** Every page should have a clear purpose, primary action, and information
  hierarchy.
- **UX-CLARITY-002 (should):** Similar actions, controls, terminology, and layouts should behave consistently
  throughout the application.
- **UX-CLARITY-003 (should):** Labels should use familiar domain language and describe outcomes rather than
  implementation details.
- **UX-CLARITY-004 (should):** Essential instructions should appear where they are needed, not only in
  external documentation.

## Navigation and Orientation

- **UX-NAV-001 (should):** Users should always understand where they are, what they can do, and how to
  return to the previous meaningful context.
- **UX-NAV-002 (should):** Navigation should reflect user tasks and permissions rather than the internal
  data model.
- **UX-NAV-003 (must):** Common destinations must be reachable predictably; dashboards should summarize
  work without becoming the only route to underlying records.
- **UX-NAV-004 (should):** URLs should be stable, meaningful, and preserve shareable state when practical.

## Accessibility

- **UX-ACCESS-001 (must):** Controls must have programmatically associated names, instructions, states,
  and validation messages.
- **UX-ACCESS-002 (must):** Color must not be the only means of conveying information, and text and
  interactive elements must meet required contrast ratios.
- **UX-ACCESS-003 (should):** Semantic elements should be preferred; assistive technology announcements
  should be added for meaningful dynamic updates.
- **UX-ACCESS-004 (must):** Motion must respect reduced-motion preferences and avoid unnecessary flashing
  or movement.

## Responsive and Adaptive Design

- **UX-RESPONSIVE-001 (must):** Core workflows must remain usable across supported viewport sizes, zoom
  levels, input methods, and text sizes.
- **UX-RESPONSIVE-002 (should):** Layouts should adapt to available space without hiding essential actions or
  requiring horizontal scrolling, except for intrinsically wide content.
- **UX-RESPONSIVE-003 (must):** Touch targets must be large enough and sufficiently separated for reliable
  use.
- **UX-RESPONSIVE-004 (must):** Responsive changes must preserve content priority and task completion, not
  merely rearrange pixels.

## Forms and Data Entry

- **UX-FORM-001 (should):** Forms should request only information required for the current task.
- **UX-FORM-002 (must):** Fields must have persistent labels, appropriate input types, sensible defaults,
  and clear required or optional status.
- **UX-FORM-003 (should):** Known context should be prefilled or displayed read-only; users should not
  re-enter information the application already knows.
- **UX-FORM-004 (should):** Validation should occur at useful times, preserve entered data, identify the
  affected field, and explain how to correct the problem.
- **UX-FORM-005 (must):** Submission must provide immediate feedback and prevent accidental duplicate
  actions without blocking intentional retries.

## Feedback and System Status

- **UX-FEEDBACK-001 (must):** Every user action must produce timely, perceivable feedback.
- **UX-FEEDBACK-002 (must):** Loading, success, empty, partial, offline, and error states must be designed
  explicitly.
- **UX-FEEDBACK-003 (should):** Long-running operations should communicate progress or ongoing activity and
  allow safe cancellation when practical.
- **UX-FEEDBACK-004 (should):** Error messages should state what happened, what remains unchanged, and what
  the user can do next without exposing sensitive implementation details.

## Safety and Control

- **UX-SAFETY-001 (must):** Destructive or difficult-to-reverse actions must clearly identify their scope
  and consequences before execution.
- **UX-SAFETY-002 (should):** Confirmation should be reserved for consequential actions; routine actions
  should use direct manipulation and reversible outcomes where practical.
- **UX-SAFETY-003 (should):** Users should be able to cancel, go back, or recover without losing work when
  technically feasible.
- **UX-SAFETY-004 (must):** Defaults must favor privacy, security, and the least surprising outcome.

## Content and Visual Design

- **UX-CONTENT-001 (should):** Content should be concise, specific, and written in plain language appropriate
  to the audience.
- **UX-CONTENT-002 (should):** Typography, spacing, color, and emphasis should establish a consistent visual
  hierarchy rather than decorate without purpose.
- **UX-CONTENT-003 (must):** Icons must not replace labels when their meaning may be ambiguous.
- **UX-CONTENT-004 (must):** Dates, times, numbers, currencies, and units must use the user's relevant
  locale and include enough context to avoid ambiguity.

## Visual Design Governance

- **UX-VISUAL-001 (must):** Established visual design rules must be recorded in
  a maintained visual-rules document that identifies their scope, rationale,
  expected behavior, relevant states, implementation implications, actionable
  requirements, useful examples or references, known exceptions, and adoption status.
- **UX-VISUAL-002 (must):** Before a visual rule is added or changed after UX
  implementation has begun, the project must assess affected screens and
  components, existing inconsistencies, migration strategy, verification needs,
  design and engineering effort, rollout risk, and remediation cost.
- **UX-VISUAL-003 (must):** A visual-rule decision must state whether it applies
  retroactively, prospectively, or incrementally and must record approved
  exceptions and follow-up work.
- **UX-VISUAL-004 (should):** Visual rules should address applicable design
  tokens, typography, color, spacing, density, hierarchy, alignment, grouping,
  component states, responsive behavior, motion, and content presentation.

## Collaborative Visual Rule Development

- **UX-DISCOVERY-001 (must):** When roadmap work requires UX elements, defining
  and documenting the applicable visual rules is a hard prerequisite to
  implementation.
- **UX-DISCOVERY-002 (must):** The agent must lead an interactive discovery
  process that obtains the user's design preferences and converts approved
  preferences into actionable visual rules.
- **UX-DISCOVERY-003 (must):** The agent must ask only for decisions required by
  the current work and must update the visual-rules document as those decisions
  are made.
- **UX-DISCOVERY-005 (must):** A user-requested UI change during iteration must
  be treated as a general rule for subsequent work in the same component,
  workflow, or visual context unless the user explicitly identifies it as an
  exception.
- **UX-DISCOVERY-006 (must):** The agent must document the inferred scope of an
  iterative visual rule and ask for clarification only when ambiguity would
  materially change the implementation or propagation of that rule.
- **UX-DISCOVERY-007 (must):** Unresolved visual decisions required by the
  current UX work must remain explicit blockers and must not be silently chosen
  by the agent.

## UX Verification

- **UX-VERIFY-001 (must):** Critical workflows must be tested at representative small and large
  viewports.
- **UX-VERIFY-002 (should):** Automated accessibility checks should run in CI, but they do not replace
  manual accessibility review.
- **UX-VERIFY-003 (should):** UX acceptance criteria should cover completion, failure, empty, loading, and
  permission-restricted states.
- **UX-VERIFY-004 (should):** Significant workflows should be evaluated with representative users or domain
  experts when practical.
