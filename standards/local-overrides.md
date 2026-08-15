# Adoption and Local Overrides

Place `.standards.yml` at the root of an adopting repository:

```yaml
standard:
  source: "https://example.com/universal-standards"
  version: "1.0.0"

overrides:
  - rule: "UX-ACCESS-002"
    action: "disable"
    scope: "/"
    reason: "The kiosk interface does not accept keyboard input."
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

Local rule IDs must begin with `LOCAL-`, follow the universal rule format, and
must not impersonate or redefine a universal rule.

## Validation and Review

Projects should validate `.standards.yml` in CI and produce the effective rules
for each applicable scope. Expired overrides are invalid. Review dates are
advisory but should be reported when overdue.

When a universal rule changes, the adopting project should revalidate all
targeted overrides. An override remains attached to its stable rule ID but must
be reviewed if the rule's meaning or requirement level changes.
