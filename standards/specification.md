# Standards Specification

## Rule Format

Every normative rule must be a list item in this form:

```text
- **RULE-ID (level):** Requirement text.
```

Each rule has:

- a permanent, unique identifier composed of uppercase segments separated by
  hyphens
- a requirement level of `must`, `should`, or `may`
- one independently overrideable requirement
- enough context to be understood without relying on its list position

Rule identifiers must not be reused after removal. Moving or rewriting a rule
does not change its identifier unless its meaning changes materially. A rule
that combines independently enforceable requirements should be split.

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

Adopting projects must pin a version. Implementations must not silently apply a
different major or minor version.

## Override Model

Overrides are explicit records targeting rule IDs. An override may:

- `replace` the rule within its scope
- `disable` the rule within its scope
- `strengthen` a `should` or `may` rule without weakening its original behavior

An override must include a non-empty reason. `replace` and `strengthen` must
include replacement text. Overrides may include an owner, review date, and
expiration date.

Override precedence is:

1. universal rule
2. repository-wide override
3. directory-scoped override

The most specific matching directory scope wins. Two overrides at the same
scope may not target the same rule. Local configuration cannot introduce a new
universal rule ID; project-only rules must use the `LOCAL-` prefix.

## Conformance

A project conforms when it:

- pins the standards version it evaluates
- records all deviations from `must` and `should` rules as valid overrides
- applies overrides only within their declared scope
- rejects unknown rule IDs, invalid actions, missing reasons, duplicate targets,
  invalid scopes, and expired overrides
- reports the effective rule set used for verification

Conformance describes traceability to the effective rules, not compliance with
every unmodified universal rule.
