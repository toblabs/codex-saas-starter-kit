# AI Coding Starter Kit (Codex Optimized)

This repository provides a **document‑driven AI development workflow**
optimized for **OpenAI Codex**.

The goal is to allow AI agents and developers to collaborate through
**explicit artifacts** instead of ad‑hoc prompts.

The project follows a structured pipeline:

Idea → PRD → Feature Specs → Architecture → Implementation → QA → Deployment


# Core Concept

Instead of writing code directly from prompts, development is driven by **repository artifacts**:

-   Product requirements
-   Feature specifications
-   Architecture documentation
-   Explicit implementation rules

Agents read these artifacts before implementing anything.

This makes AI‑driven development:

-   deterministic
-   auditable
-   maintainable


# Tech Stack

The repository assumes the following stack:

### Frontend

-   Next.js (App Router)
-   TypeScript
-   Tailwind CSS
-   shadcn/ui
-   react-hook-form
-   Zod

### Backend

-   Supabase
-   PostgreSQL

### Infrastructure

-   Vercel
-   Environment variables via `.env.local`


# Repository Structure
```
    .
    ├── AGENTS.md
    ├── docs
    │   ├── PRD.md
    │   ├── features
    |   │   ├── INDEX.md
    |   │   └── PROJ-X-feature.md
    │   └── production
    │
    ├── features
    │   ├── INDEX.md
    │   ├── _TEMPLATE.md
    │   └── PROJ-X-feature.md
    │
    ├── .codex
    │   └── skills
    │       ├── requirements
    │       ├── architecture
    │       ├── frontend
    │       ├── backend
    │       ├── qa
    │       └── deploy
    │
    └── src

```

# Development Workflow

## 1. Define the Product

Start by describing the product vision inside:

`docs/PRD.md`

The PRD describes:
-   product vision
-   users
-   MVP scope
-   feature themes

## 2. Define Features

Break the product into features:

`features/PROJ-X-feature-name.md`

Track them in:

`features/INDEX.md`

## 3. Architecture

Document the tech design in:

`features/PROJ-X-feature-name.md`

## 4. Implementation

Implementation follows the feature specification and architecture.

Agents use dedicated skills:

-   requirements
-   architecture
-   frontend
-   backend
-   qa
-   deploy


# Using Codex

Typical workflow inside Codex:


### 1 Create PRD
```
Use the requirements skill to initialize the PRD for a new project.

Project idea:
<description>

Tasks:
1. Populate docs/PRD.md
2. Define product vision
3. Identify user groups
4. Define MVP scope
5. Suggest initial feature themes

Do not implement code.
Do not create feature specs yet.
```

### 2 Generate Features

**After creating initial PRD:**
```
Use the requirements skill.

Based on docs/PRD.md, create the first MVP feature specs.
```

**For a new feature:**
```
Use the requirements skill.

Feature idea:
<description>

Based on this feature idea, create needed feature specs.
```

### 3 Design Architecture
```
Use the architecture skill for PROJ-1.

Check, which implementation skills are needed:
- Frontend
- Backend
```

### 4 Implement Feature
```
Use the frontend skill to implement PROJ-1.

Check first if frontend skill is needed.
```

### 5 Backend Implementation
```
Use the backend skill for PROJ-1.

Check first if backend skill is needed.
```

### QA
```
Use the QA skill to verify PROJ-1.
```

### Deployment
```
Use the deploy skill to prepare the feature for production.
```


# Feature Lifecycle

Each feature moves through these states:
```
Draft → Planned → In Progress → Review → Done → Deployed
```


# Rules

Agents must always:

-   read files before editing
-   follow the defined tech stack
-   reuse existing components
-   prefer shadcn/ui primitives
-   validate runtime inputs using Zod
-   respect authentication and authorization boundaries
-   avoid introducing alternative frameworks


# Commands

Install dependencies
```bash
npm install
```
Run development server
```bash
npm run dev
```
Build project
```bash
npm run build
```
Lint
```bash
npm run lint
```


# Goal of this Repository

This repository demonstrates a **structured AI‑assisted developmentworkflow** where:

-   requirements drive implementation
-   architecture is explicit
-   features are traceable
-   AI agents operate deterministically

Instead of "vibe coding", the system enables **repeatable AI engineering workflows**.
