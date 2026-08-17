# Application Implementation Standard

## Code Comments

- **IMPL-COMMENT-001 (must):** Code comments must follow the universally accepted comment-formatting standard
  for the implementation language when one exists.
- **IMPL-COMMENT-002 (must):** When an implementation language has multiple competing comment-formatting
  standards and the project has not established one, one standard must be explicitly selected before comments
  are added.
- **IMPL-COMMENT-003 (must):** Code comments must communicate meaningful context rather than reiterate names or
  behavior that are evident from the code.
- **IMPL-COMMENT-004 (must):** Code comments must use clear narrative prose written for human readers.
- **IMPL-COMMENT-005 (must):** `TODO` and `FIXME` comments must not be used; required follow-up work must instead
  be completed in the current change or tracked in the project's designated issue system.

## Separation of Concerns

- **IMPL-SEPARATION-001 (should):** Presentation code should describe structure and display prepared state; it
  should not own business rules, authorization, persistence queries, or complex
  data transformation.
- **IMPL-SEPARATION-002 (should):** Business rules, data access, presentation preparation, and delivery concerns
  should have explicit boundaries appropriate to the chosen architecture.
- **IMPL-SEPARATION-003 (should):** Components and services should have focused responsibilities and stable,
  testable interfaces.

## Server Authority and Trust Boundaries

- **IMPL-TRUST-001 (must):** The server must remain authoritative for authorization, validation, persisted
  state, and security-sensitive decisions.
- **IMPL-TRUST-002 (must):** Client-side visibility, disabled controls, hidden fields, route parameters,
  and cached state must never be treated as authorization controls.
- **IMPL-TRUST-003 (must):** Every untrusted input must be validated and normalized at a defined boundary.
- **IMPL-TRUST-004 (must):** Data selections and mutations must be restricted to the authenticated user's
  authorized scope.

## Contextual Workflows

- **IMPL-CONTEXT-001 (should):** Actions should begin from the richest safe context available.
- **IMPL-CONTEXT-003 (should):** Contextual entry points should be preferred when
  they reduce ambiguity or invalid choices; global entry points may remain as
  fallbacks.
- **IMPL-CONTEXT-004 (must):** Submitted context must be revalidated by the server before use.

## Collections and Data Exploration

- **IMPL-COLLECTION-001 (must):** Collection operations must be applied in this order: authorization scope,
  search and filtering, sorting, then pagination.
- **IMPL-COLLECTION-002 (must):** Operations over incomplete or paginated datasets must execute against the
  authoritative dataset, not only the records currently rendered in the client.
- **IMPL-COLLECTION-003 (may):** Client-side sorting and filtering may be used only when the complete bounded
  dataset is present and the behavior is explicitly designed for it.
- **IMPL-COLLECTION-004 (must):** Searchable, filterable, and sortable fields must be allowlisted; request input
  must not directly define queries or executable expressions.
- **IMPL-COLLECTION-005 (should):** Changes that can shrink a result set should reset invalid pagination state.

## Consistency and Reuse

- **IMPL-CONSISTENCY-005 (must):** Until a human approves another product name, placeholder product names must
  be derived only by case-converting the name of the containing project directory.
- **IMPL-CONSISTENCY-001 (should):** Repeated interaction patterns should use shared abstractions with declarative
  configuration and safe defaults.
- **IMPL-CONSISTENCY-002 (should):** Abstractions should hide replaceable implementation details without obscuring
  domain behavior.
- **IMPL-CONSISTENCY-003 (should):** User-visible changes should include representative development or demo data
  when such data is necessary to exercise the workflow meaningfully.
