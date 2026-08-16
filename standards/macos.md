# macOS Development Standard

## Host Dependency Isolation

- **MACOS-ENV-001 (must):** Application build, test, and runtime commands must execute through the project's
  Docker environment rather than directly on the macOS host.
- **MACOS-ENV-002 (must):** The macOS host must require no project tooling beyond Docker and operating-system
  supplied utilities unless a named exception receives explicit human approval.
