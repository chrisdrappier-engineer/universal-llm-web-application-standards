# Quality and Verification Standard

## Definition of Done

- **QUALITY-DONE-001 (must):** A change is complete only when implementation, tests, static analysis,
  documentation, configuration, and representative data are updated as needed.
- **QUALITY-DONE-002 (must):** User-facing workflow changes must include end-to-end coverage or a documented
  reason that such coverage provides no meaningful value.
- **QUALITY-DONE-003 (must):** Verification must be proportional to the change's risk and must exercise the
  affected behavior, not merely adjacent code.

## Layered Verification

- **QUALITY-LAYERS-001 (should):** Formatting, linting, type checking, dependency validation, and security checks
  should run automatically where applicable.
- **QUALITY-LAYERS-002 (should):** Focused tests should cover business rules, authorization, validation, boundary
  conditions, and failure paths.
- **QUALITY-LAYERS-003 (should):** Integration tests should verify contracts across application boundaries.
- **QUALITY-LAYERS-004 (should):** End-to-end tests should exercise critical workflows through visible user
  controls; direct internal navigation is appropriate only when testing routing
  or deep-link behavior.
- **QUALITY-LAYERS-005 (should):** Runtime verification should include application startup and a health or smoke
  check in a production-representative environment when practical.

## Test Design

- **QUALITY-TEST-001 (must):** Tests must be deterministic, isolated, repeatable, and clear about the behavior
  they protect.
- **QUALITY-TEST-002 (should):** Test data should be minimal but sufficient for the behavior under test.
- **QUALITY-TEST-003 (should):** Collection tests should cover authorization scoping, thresholds, filtering,
  sorting, pagination recalculation, invalid state, and input allowlisting.
- **QUALITY-TEST-004 (must):** Flaky tests must be fixed or quarantined with an owner and rationale; they must
  not be silently retried until green.

## Continuous Integration

- **QUALITY-CI-001 (should):** The canonical verification pipeline should be executable locally and in CI.
- **QUALITY-CI-002 (must):** CI must fail on any required verification failure and must clean up resources
  it creates.
- **QUALITY-CI-003 (should):** Tool versions and runtime boundaries should be reproducible.
- **QUALITY-CI-004 (should):** Generated artifacts and evidence should identify the application and tooling
  versions that produced them when interpretation depends on those versions.

## Reporting

- **QUALITY-REPORT-001 (should):** Verification reports should name the checks run and whether they passed.
- **QUALITY-REPORT-002 (must):** Known gaps, skipped checks, environmental limitations, and residual risks must
  be stated explicitly.
- **QUALITY-REPORT-003 (should):** Raw logs should be retained by tooling but summarized for human review.
