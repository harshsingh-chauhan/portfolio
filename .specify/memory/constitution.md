<!--
Sync Impact Report:
- Version change: N/A -> 1.0.0
- Added sections:
  - Core Principles
  - Technology Stack
  - Development Workflow
  - Governance
- Templates requiring updates:
  - ✅ .specify/templates/plan-template.md
  - ✅ .specify/templates/spec-template.md
  - ✅ .specify/templates/tasks-template.md
- Follow-up TODOs: None
-->
# Arjun Sharma's Professional Portfolio Website Constitution

## Core Principles

### I. Atomic Design Methodology
The project MUST follow Brad Frost's Atomic Design methodology. UI components will be built hierarchically (Atoms → Molecules → Organisms → Templates → Pages). This ensures a scalable, maintainable, and consistent component system.

### II. Component-Driven Development
Every UI component (Atoms, Molecules, Organisms) MUST be developed in isolation using Storybook. This facilitates independent testing, documentation, and reusability before integration into the main application.

### III. Design System Adherence
The project MUST adhere to the defined Design Specifications. This includes the professional blue color scheme, Inter/Fira Code typography, and DaisyUI component library. The goal is a consistent and professional visual identity.

### IV. Performance as a Feature
The application MUST meet the defined performance targets (Lighthouse >90, FCP <1.5s, TTI <3.0s). This includes code splitting, lazy loading of images, and bundle size optimization. User experience depends on a fast and responsive interface.

### V. Quality and Accessibility
The project MUST achieve high standards of technical quality and accessibility. This includes strict TypeScript, no linting errors, and WCAG 2.1 AA compliance (Lighthouse Accessibility >90).

## Technology Stack

- **Framework**: React 19+
- **Language**: TypeScript 5.7+ (Strict Mode)
- **Styling**: TailwindCSS 4.1+ with DaisyUI 5+
- **Build Tool**: Vite 8+
- **Animation**: GSAP 3.12+
- **Version Control**: Git + GitHub

## Development Workflow

The development process MUST follow the "Build from smallest to largest" approach outlined in the PRD. All new components must first be created and tested as atoms or molecules in Storybook before being composed into larger organisms. All code must be reviewed via GitHub Pull Requests before merging to the `main` branch.

## Governance

This constitution is the single source of truth for project standards. All development, code reviews, and decisions must align with these principles. Any deviation requires a formal amendment to this document. The PRD (`PRD.md`) serves as the primary guidance for feature implementation under this constitution.

**Version**: 1.0.0 | **Ratified**: 2025-12-25 | **Last Amended**: 2025-12-25