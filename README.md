# Universal Web Application Development Standards

This repository defines reusable standards for web application projects built
with an LLM-assisted development workflow. The standards are intentionally
independent of programming language, framework, database, cloud platform, and
LLM product.

## Standards

- [Standards Specification](standards/specification.md)
- [Adoption and Local Overrides](standards/local-overrides.md)
- [AI-Assisted Development](standards/ai-workflow.md)
- [Application Implementation](standards/implementation.md)
- [Dependency Selection](standards/dependencies.md)
- [macOS Development](standards/macos.md)
- [Docker](standards/docker.md)
- [User Experience](standards/user-experience.md)
- [Quality and Verification](standards/quality.md)
- [Standards Review Log](standards/review-log.md)

## Adoption

Adopting projects should pin a released standards version and add a
`.standards.yml` file at the repository root. See [Adoption and Local
Overrides](standards/local-overrides.md) for the configuration format.

Project-specific rules override these standards only when the override is
intentional and documented.
