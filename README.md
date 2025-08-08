# Cursor Rules

A curated set of reusable Cursor rules to accelerate architecture, bootstrapping, testing, security, QA, and refactoring across projects.

## What this repo contains

- `rules/*.mdc`: Rule cards with frontmatter, scopes, and checklists you can apply in Cursor chats.
- Each rule is intentionally focused, non–always-on (`alwaysApply: false`), and includes an output template to standardize deliverables.

## Quick start

Use these rules in any project in one of two ways:

1. Workspace-scoped (recommended)

- Copy or symlink the files into your project's `.cursor/rules/` folder so they travel with the codebase.

```bash
mkdir -p .cursor/rules && cp -R rules/* .cursor/rules/
```

2. Global install in Cursor

- In Cursor, open Settings → Rules → Import from folder and select this repo's `rules/` directory.

## Using a rule in chat

- Open a chat in Cursor and explicitly invoke a rule when relevant. Examples:
  - “Apply Project Planner to break down this feature and coordinate frontend, backend, QA, and security.”
  - “Use API Architect to design the REST/GraphQL API and DB schema for these requirements.”
  - “Use SwiftUI Expert to refactor this view using modern data flow patterns.”
- You can also open the Rules panel in Cursor, select a rule, and apply it to the current conversation.

## Rules overview

- API Architect (`api-architect.mdc`) — design and implement backend APIs (REST/GraphQL), DB schema, auth, security, deployment.
- Refactoring Architect (`refactoring-architect.mdc`) — analyze and refactor code structure to improve maintainability.
- Next.js Bootstrapper (`nextjs-bootstrapper.mdc`) — spin up a production-ready Next.js app (TS + Tailwind + App Router).
- Project Planner (`project-planner.mdc`) — break down complex work and coordinate across domains.
- QA Engineer (`qa-engineer.mdc`) — define test strategy and implement tests.
- Security Auditor (`security-auditor.mdc`) — run a targeted security audit; prioritize findings.
- SwiftUI Expert (`swiftui-expert.mdc`) — build/refactor SwiftUI using iOS 18+ patterns.

## When to use each rule

- **API Architect**

  - Frontend needs a backend API from scratch or an existing API needs redesign.
  - Decisions involve API style (REST/GraphQL), database schema, auth, and deployment.
  - Real-time features or performance shaping required.

- **Refactoring Architect**

  - Code cleanup or structure improvements are requested.
  - Large/complex files, mixed responsibilities, or business logic in UI/controllers.
  - Inconsistent patterns or duplicated logic across the codebase.

- **Next.js Bootstrapper**

  - Starting a new Next.js project or cloning structure from an existing repo.
  - Need modern setup: App Router, TypeScript strict, Tailwind, ESLint/Prettier.

- **Project Planner**

  - Work spans multiple domains (UI, API, DB, security, tests) or needs sequencing.
  - Stakeholders want a roadmap, breakdown, or delegation strategy.

- **QA Engineer**

  - No tests yet, or coverage is incomplete/outdated.
  - New feature added that needs unit/integration/e2e tests.
  - Pre-release verification required.

- **Security Auditor**

  - New or changed auth flows; preparing for security review.
  - Risk of credential exposure or cloud configuration changes.

- **SwiftUI Expert**
  - SwiftUI UI implementation or refactoring.
  - Adopting iOS 18+ APIs, decomposing large views, or improving state management.

## Conventions and behavior

- Scopes via `globs`: Each rule lists file globs that hint when it's relevant. This helps keep responses focused.
- `alwaysApply: false`: Rules only run when you explicitly ask for them, keeping normal conversations lightweight.
- Output templates: Each rule provides a consistent structure (plans, checklists, or reports) to speed up delivery and review.

## Customize or add a new rule

1. Duplicate any `.mdc` file in `rules/`.
2. Update the frontmatter `description`, `globs`, and `alwaysApply` as needed.
3. Keep the rule under ~500 lines, include a clear checklist, and add a concise output template.

## Suggested entry point

- Start with `Project Planner` to outline the plan, then hand off specific tasks to `api-architect`, `nextjs-bootstrapper`, `swiftui-expert`, `qa-engineer`, `security-auditor`, and `refactoring-architect` as appropriate.
