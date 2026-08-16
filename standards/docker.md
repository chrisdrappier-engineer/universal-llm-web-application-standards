# Docker Standard

## Base Image

- **DOCKER-BASE-001 (must):** Each project must declare and pin its own Debian slim base-image version and must
  not use an unversioned or `latest` image reference.

## Dependency Isolation

- **DOCKER-DEPS-001 (must):** Every project-specific system or language dependency must be declared and
  installed inside the project's containers.
- **DOCKER-DEPS-002 (must):** Every language dependency must be declared in the ecosystem's project-level
  dependency manifest and resolved through its package manager.
- **DOCKER-DEPS-003 (must):** Dependency manifests and complete lockfiles, or equivalent reproducible-resolution
  artifacts, must be tracked in the repository.
- **DOCKER-DEPS-004 (must):** Container builds and CI must install the locked dependency state in frozen or
  immutable mode and fail when manifests and lockfiles disagree.

## Environments

- **DOCKER-ENV-001 (must):** Every newly established project must provide `development` and `test` Docker
  environments.
- **DOCKER-ENV-002 (must):** The `development` and `test` environments must be independently buildable from
  shared project-owned configuration.
- **DOCKER-ENV-003 (must):** The `development` environment must support interactive use.
- **DOCKER-ENV-004 (must):** The `development` environment must support source-mounted fast iteration.
- **DOCKER-ENV-005 (must):** The `development` environment must provide required debugging tools.
- **DOCKER-ENV-006 (must):** The `development` environment must support persistent dependency caches.
- **DOCKER-ENV-007 (must):** The `test` environment must run non-interactively.
- **DOCKER-ENV-008 (must):** The `test` environment must run from repository state without source bind mounts
  or dependence on developer-specific state.
- **DOCKER-ENV-009 (must):** The `test` environment must isolate each run.
- **DOCKER-ENV-010 (must):** The `test` environment must exit successfully only when its required verification
  succeeds.
