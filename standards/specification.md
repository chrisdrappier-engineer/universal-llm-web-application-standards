# Standards Specification

## Rule Format

- **SPEC-FORMAT-001 (must):** Every normative rule must be a list item in this form:

```text
- **RULE-ID (level):** Requirement text.
```

- **SPEC-FORMAT-002 (must):** Each rule must have a permanent, unique identifier composed of uppercase
  segments separated by hyphens.
- **SPEC-FORMAT-006 (must):** Each rule must declare a requirement level of `must`, `should`, or `may`.
- **SPEC-FORMAT-003 (must):** Each rule must contain one independently overrideable requirement with enough
  context to be understood without relying on its list position.
- **SPEC-FORMAT-004 (must):** Rule identifiers must not be reused after removal.
- **SPEC-FORMAT-005 (must):** Moving or rewriting a rule must not change its identifier unless its meaning
  changes materially.

## Requirement Levels

- `must` is required unless an applicable local override replaces or disables it.
- `should` is the default expectation; deviations require an applicable override
  with a reason.
- `may` grants permission and does not require adoption or an override when unused.

Descriptive text, headings, examples, and rationale are non-normative unless
they contain an identified rule.

## Standards Versioning

Published standards use semantic versions:

- major: removes a rule, changes a rule's meaning incompatibly, or changes
  configuration semantics
- minor: adds rules or adds backward-compatible configuration capabilities
- patch: clarifies wording without changing required behavior

- **SPEC-VERSION-001 (must):** Adopting projects must pin the standards version they evaluate.
- **SPEC-VERSION-002 (must):** Implementations must not silently apply a different major or minor version.

## Override Model

Overrides are explicit records targeting rule IDs. An override may:

- `replace` the rule within its scope
- `disable` the rule within its scope
- `strengthen` a `should` or `may` rule without weakening its original behavior

- **SPEC-OVERRIDE-001 (must):** Every override must include a non-empty reason.
- **SPEC-OVERRIDE-002 (must):** A `replace` or `strengthen` override must include replacement text.
- **SPEC-OVERRIDE-003 (may):** Overrides may include an owner, review date, and expiration date.

Override precedence is:

1. universal rule
2. repository-wide override
3. directory-scoped override

- **SPEC-OVERRIDE-004 (must):** The most specific matching directory override must take precedence.
- **SPEC-OVERRIDE-005 (must):** Two overrides at the same scope must not target the same rule.
- **SPEC-OVERRIDE-006 (must):** Local configuration must not introduce a universal rule ID; project-only
  rules must use the `LOCAL-` prefix.

## Consistency and Redundancy

- **SPEC-REVIEW-001 (must):** Before a rule is added or materially changed, it must be compared with every
  existing rule whose scope or subject overlaps it to identify contradictions, incompatible requirement
  levels, and duplicate obligations.
- **SPEC-REVIEW-002 (must):** A new rule must not restate an obligation already governed by an existing rule;
  the existing rule must be clarified or expanded instead when one canonical rule can govern the behavior.
- **SPEC-REVIEW-003 (must):** Intentional overlap must have distinct enforcement boundaries, and the rules'
  wording must make those boundaries independently understandable.
- **SPEC-REVIEW-004 (must):** A standards change must record the rule IDs reviewed and any conflict,
  consolidation, retirement, or intentional overlap found.

## Conformance

- **SPEC-CONFORMANCE-001 (must):** A conforming project must pin the standards version it evaluates.
- **SPEC-CONFORMANCE-002 (must):** A conforming project must record every deviation from a `must` or `should`
  rule as a valid override.
- **SPEC-CONFORMANCE-003 (must):** A conforming project must apply overrides only within their declared scope.
- **SPEC-CONFORMANCE-004 (must):** A conforming project must reject unknown rule IDs, invalid actions, missing
  reasons, duplicate targets, invalid scopes, and expired overrides.
- **SPEC-CONFORMANCE-005 (must):** A conforming project must report the effective rule set used for verification.

Conformance describes traceability to the effective rules, not compliance with
every unmodified universal rule.
