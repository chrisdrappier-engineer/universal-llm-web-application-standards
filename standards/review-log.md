# Standards Review Log

## 2026-08-17: Public Standards Source

- Added `ADOPT-SOURCE-001`, requiring adopting projects to use the hardcoded public GitHub origin rather than
  discovering an origin or referencing a local filesystem source.
- Reviewed `ADOPT-CONFIG-001`, `SPEC-VERSION-001`, `SPEC-VERSION-002`, and `SPEC-CONFORMANCE-001`.
- The new rule governs source location; the existing rules govern configuration placement and version pinning.
  No conflict or redundant obligation found.

## 2026-08-17: Code Commenting

- Added `IMPL-COMMENT-001` through `IMPL-COMMENT-005`, governing comment formatting, content, human-readable
  prose, and follow-up work tracking.
- Reviewed `AI-CONTEXT-001`, `AI-EXECUTION-005`, `QUALITY-DONE-001`, and `QUALITY-CI-004`.
- Existing rules govern repository documentation, change scope, completion, and artifact traceability; the new
  rules govern comments embedded in source code. No conflict or redundant obligation found.

## 2026-08-16: Docker Environments and Dependency Governance

- Added `DOCKER-DEPS-002` through `DOCKER-DEPS-004` and `DOCKER-ENV-001` through `DOCKER-ENV-010`.
- Added `DEPENDENCY-SELECTION-001` through `DEPENDENCY-SELECTION-003` and `DEPENDENCY-DISCOVERY-001` through
  `DEPENDENCY-DISCOVERY-003`.
- Reviewed `AI-AUTHORITY-*`, `AI-EXECUTION-*`, `QUALITY-DONE-*`, `QUALITY-LAYERS-*`, and `QUALITY-CI-*`.
- Docker rules govern dependency installation and execution environments; dependency rules govern discovery,
  evaluation, and approval. Existing quality rules retain verification ownership. No conflict or redundant
  obligation found.

## 2026-08-16: macOS and Docker Dependency Isolation

- Added `MACOS-ENV-001` and `MACOS-ENV-002`, requiring Docker-based execution without project-specific macOS
  host dependencies.
- Added `DOCKER-BASE-001` and `DOCKER-DEPS-001`, requiring a project-pinned Debian slim image and containerized
  dependencies.
- Reviewed `AI-AUTHORITY-*`, `AI-EXECUTION-*`, and `QUALITY-CI-*`.
- The macOS rules govern host policy, while the Docker rules govern container implementation; existing rules
  retain approval, execution, and reproducibility ownership. No conflict or redundant obligation found.

## 2026-08-16: Consistency and Redundancy Review

- Consolidated `AI-EXECUTION-004` into `QUALITY-DONE-001`.
- Consolidated `IMPL-CONTEXT-002` into `UX-FORM-003`.
- Narrowed `IMPL-COLLECTION-005`; shareable URL behavior remains governed by `UX-NAV-004`.
- Consolidated `IMPL-CONSISTENCY-004` into the applicable `UX-ACCESS-*`, `UX-RESPONSIVE-*`, and
  `UX-FEEDBACK-*` rules.
- Consolidated `UX-DISCOVERY-004` into `UX-VISUAL-001`.
- Corrected the `UX-RESPONSIVE-003` override example and converted specification and adoption requirements
  to identified rules.
- Added `SPEC-REVIEW-001` through `SPEC-REVIEW-004`; no unresolved conflict or intentional overlap remains.
