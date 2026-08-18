# Adoption and Local Overrides

- **ADOPT-CONFIG-001 (must):** An adopting repository must place `.standards.yml` at its root.

```yaml
standard:
  source: "https://github.com/chrisdrappier-engineer/universal-llm-web-application-standards.git"
  version: "0.4.0"

overrides:
  - rule: "UX-RESPONSIVE-003"
    action: "disable"
    scope: "/"
    reason: "The fixed wall display has no touch input."
    owner: "product-platform"
    review_on: "2027-01-15"

  - rule: "IMPL-COLLECTION-003"
    action: "replace"
    scope: "/examples/static-catalog/"
    reason: "The complete catalog is bundled and bounded to 100 records."
    text: "Filtering may execute in the client over the bundled catalog."
    expires: "2027-06-30"
```

## Configuration Fields

- `standard.source` identifies the adopted standards distribution.
- `standard.version` pins the evaluated semantic version.
- `overrides` is a list of explicit deviations.
- `rule` is the stable universal rule ID.
- `action` is `replace`, `disable`, or `strengthen`.
- `scope` is `/` for the repository or an absolute repository-relative directory
  ending in `/`; files beneath it inherit the override.
- `reason` explains why the universal rule does not fit.
- `text` is required for `replace` and `strengthen`.
- `owner`, `review_on`, and `expires` are optional governance metadata.

- **ADOPT-SOURCE-001 (must):** `standard.source` must be
  `https://github.com/chrisdrappier-engineer/universal-llm-web-application-standards.git`.

## Local Project Rules

Projects may append rules that do not override universal rules:

```yaml
rules:
  - id: "LOCAL-DATA-001"
    level: "must"
    scope: "/"
    text: "Production data must remain in the approved region."
    reason: "Contractual data-residency requirement."
```

- **ADOPT-LOCAL-001 (must):** Local rule IDs must begin with `LOCAL-`.
- **ADOPT-LOCAL-002 (must):** Local rules must follow the universal rule format.
- **ADOPT-LOCAL-003 (must):** Local rules must not impersonate or redefine a universal rule.

## Validation and Review

- **ADOPT-VALIDATE-001 (should):** Projects should validate `.standards.yml` in CI.
- **ADOPT-VALIDATE-002 (should):** Projects should produce the effective rules for each applicable scope.
- **ADOPT-VALIDATE-003 (must):** Expired overrides must be rejected as invalid.
- **ADOPT-VALIDATE-004 (should):** Overdue advisory review dates should be reported.

- **ADOPT-REVIEW-001 (should):** When a universal rule changes, an adopting project should revalidate every
  override targeting it.
- **ADOPT-REVIEW-002 (must):** An override must be reviewed when its target rule's meaning or requirement
  level changes.
