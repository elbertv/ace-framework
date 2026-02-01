# Changelog

All notable changes to the ACE Framework will be documented in this file.

## [v2.1.0] - 2026-02-01

### Added

- **Discuss Phase**: New phase in BMAD (between Analyze and Plan) for capturing "soft" preferences.
- **Workflow**: `.ace/workflows/discuss-phase.md` to guide the discussion process.
- **Context**: `docs/context/PROJECT_CONTEXT.md` artifact for stable project preferences.
- **XML Tasks**: `implementation_plan.md` now uses XML `<task>` tags for better Agent parsing.
- **Atomic Commits**: Strict "One Task = One Commit" rule enforced in Developer role.

### Changed

- **ACE-SPEC.md**: Updated to include Discuss phase and new documentation standards.
- **Roles**: Updated Architect and Developer roles with new responsibilities.
- **Prompts**: Updated `generate-implementation-plan.md` to output XML format.

## [v2.0.0] - Initial Standard

### Added

- **BMAD Methodology**: The core "Analyze → Plan → Execute → Verify" loop.
- **Directory Setup**: Standardized `.ace/` directory structure for Agent knowledge.
- **Agentic Roles**: Definition of 7 key roles (Architect, Developer, QA, etc.).
- **Active Context**: Protocol for maintaining session state in `ACTIVE_CONTEXT.md`.
- **RCA Protocol**: Standardized Root Cause Analysis and Regression Guards.
- **ADR System**: Architecture Decision Records for tracking design choices.

## [v1.0] - Pre-history (The "Conversation" Era)

### Conceptual

- Represents the ad-hoc usage of LLMs without standardized frameworks.
- Characterized by:
  - Casual, unstructured conversations.
  - Lack of persistent context management.
  - No defined roles or responsibilities.
  - Fragile, non-reproducible outputs.
- **Note**: There are no files or specs for v1.0; it serves as the "dark age" baseline that v2.0 standardizes.
