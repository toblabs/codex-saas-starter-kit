# AI Coding Starter Kit

A Next.js template with an AI-powered development workflow using specialized skills for Requirements, Architecture, Frontend, Backend, QA, and Deployment.

## Tech Stack
- **Framework:** Next.js 16 (App Router), TypeScript
- **Styling:** Tailwind CSS + shadcn/ui
- **Backend:** Supabase (PostgreSQL + Auth + Storage) - optional
- **Deployment:** Vercel
- **Validation:** Zod + react-hook-form
- **State:** React useState / Context API

## Project Structure
```text
src/
  app/                 Pages (Next.js App Router)
  components/
    ui/                shadcn/ui components (NEVER recreate these)
  hooks/               Custom React hooks
  lib/                 Utilities (supabase.ts, utils.ts)
features/
  PROJ-X-name.md       Feature specifications
  INDEX.md             Feature status overview
docs/
  PRD.md               Product Requirements Document
  production/          Production guides (Sentry, security, performance)
  features/
    PROJ-X-name.md     Feature specifications
    INDEX.md           Feature status overview
.agents/
  skills/              Codex skills
```

## Development Workflow
1. `/requirements` - Create feature spec from idea
2. `/architecture` - Design tech architecture (PM-friendly, no code)
3. `/frontend` - Build UI components (shadcn/ui first)
4. `/backend` - Build APIs, database, RLS policies
5. `/qa` - Test against acceptance criteria + security audit
6. `/deploy` - Deploy to Vercel + production-ready checks

## Feature Tracking
All features are tracked in `docs/features/INDEX.md`. Every skill should read it at the start and update it when needed.
Feature specs live in `docs/features/PROJ-X-name.md`.

## Key Conventions
- **Feature IDs:** `PROJ-1`, `PROJ-2`, ... (sequential)
- **Commits:** `feat(PROJ-X): description`, `fix(PROJ-X): description`
- **Single Responsibility:** One feature per spec file
- **shadcn/ui first:** Never create custom versions of installed shadcn components
- **Human-in-the-loop:** Workflows include user approval checkpoints
- **Windows-first:** Prefer cross-platform commands or PowerShell-friendly equivalents when suggesting shell commands

## Rules
### New Project Detection (mandatory)
Before starting any work:
1. Read `docs/PRD.md` to check whether the project has been initialized.
2. Read `docs/features/INDEX.md` to see whether any features already exist.

If `docs/PRD.md` still contains placeholder text like `_Describe what you are building_` and `docs/features/INDEX.md` is still empty:
- Do not write code or skip ahead to implementation.
- Start with `/requirements`.

### Always read, never guess
- Read a file before modifying it.
- Verify import paths, routes, and existing patterns by reading the codebase.
- Re-read `docs/features/INDEX.md` and the referenced feature spec before each workflow step.

### Workflow discipline
- Keep state in files, not in chat memory.
- Update the relevant feature spec and `docs/features/INDEX.md` as work progresses.
- Suggest the next workflow step when a skill completes.

## Build & Test Commands
```bash
npm run dev
npm run build
npm run lint
npm run start
```

## Product Context
@docs/PRD.md

## Feature Overview
@features/INDEX.md

## Available Skills
- `.agents/skills/requirements`
- `.agents/skills/architecture`
- `.agents/skills/frontend`
- `.agents/skills/backend`
- `.agents/skills/qa`
- `.agents/skills/deploy`
- `.agents/skills/help`
