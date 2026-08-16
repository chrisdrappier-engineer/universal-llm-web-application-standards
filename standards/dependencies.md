# Dependency Selection Standard

## Selection and Approval

- **DEPENDENCY-SELECTION-001 (should):** An established package should be preferred over custom implementation
  when it adequately satisfies the requirement.
- **DEPENDENCY-SELECTION-002 (must):** Each proposed package must be presented and evaluated individually,
  including its purpose, alternatives, maintenance, security, licensing, and operational cost.
- **DEPENDENCY-SELECTION-003 (must):** A person must explicitly approve each new package before it is added or
  code depending on it is written.

## Discovery During Development

- **DEPENDENCY-DISCOVERY-001 (must):** During design, each requirement representing a common technical capability
  must trigger a package search before architecture or implementation is approved.
- **DEPENDENCY-DISCOVERY-002 (must):** During implementation, custom code must pause for a package search when it
  begins reproducing a reusable library, protocol, parser, client, framework feature, or other non-domain capability.
- **DEPENDENCY-DISCOVERY-003 (must):** Material requirement or scope changes must repeat package discovery for
  newly introduced capabilities before implementation continues.
