# if-hub

[![Super-Linter](https://github.com/aydabd/if-hub/actions/workflows/super-linter.yml/badge.svg)](https://github.com/aydabd/if-hub/actions/workflows/super-linter.yml)

## Overview

Brief project description following SOLID principles, TDD, and DDD architecture patterns.

## Architecture

This project follows:

- **SOLID principles** for maintainable code
- **Test-Driven Development** (TDD) for reliability
- **Domain-Driven Design** (DDD) for clear business logic
- **Type-safe** implementation
- **Dependency injection** for testability

## Development

### Prerequisites

List required tools and versions here.

### Setup

```bash
git clone <repository-url>
cd <repository-name>

# Install dependencies
make install
```

### Running Tests

```bash
# Run all tests
make test

# Run with coverage
make coverage
```

### Linting

```bash
# Run super-linter locally (check only)
make lint

# Run super-linter with autofix
make lint-fix
```

The repository includes GitHub Super-Linter for consistent code quality:

- **Automatic formatting** on pull requests
- **Language-agnostic linting** for Markdown, YAML, JSON, XML, and EditorConfig
- **Programming language validation** configured in `.super-linter.env`
- **Local linting** with Docker via `make lint` commands

## Code Standards

- **Indentation**: 4 spaces (code), 2 spaces (YAML/JSON)
- **Linting**: Enforced via pre-commit hooks
- **Formatting**: Autoformat before commit
- **Type safety**: Strictly enforced
- **No trailing whitespace**


## Spec-Driven Workflow

This repository now uses GitHub Spec Kit for requirements-first delivery.

- Core project rules live in `.specify/memory/constitution.md`
- The initial MVP spec lives in `specs/001-platform-foundation/`
- Planned MVP milestones live in `specs/backlog/milestones.md`
- GitHub issue templates for epics and user stories live in `.github/ISSUE_TEMPLATE/`

Recommended sequence for new work:

1. Update or create the relevant `/specs/` artifact.
2. Align the work to an epic and milestone.
3. Break the approved spec into tasks.
4. Start implementation only after the spec artifacts are approved.

## Contributing

1. Create feature branch from `main`
2. Write tests first (TDD)
3. Implement feature
4. Ensure all tests pass
5. Run linter and formatter
6. Submit PR (requires 2 approvals)

See CONTRIBUTING.md and CODEOWNERS for details.

## Testing Philosophy

- All code must be testable
- Unit tests for all modules
- Integration tests for components
- Test fixtures separated by module
- Minimum 80% coverage

## License

See LICENSE file for details.
