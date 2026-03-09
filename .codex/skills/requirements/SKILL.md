---
name: requirements
description: Turn a raw product idea into a structured, implementation-ready feature specification for this repository
---

# Requirements

## Purpose

Use this skill to turn a raw product idea into a structured, implementation-ready feature specification for this repository.

This repository is **not stack-agnostic**. Requirements must already respect the intended implementation context:

- **Next.js 16 App Router**
- **TypeScript**
- **Tailwind CSS**
- **shadcn/ui**
- **Supabase**
- **PostgreSQL**
- **Zod**
- **Vercel**

The goal is not to write abstract product prose.  
The goal is to produce feature specs that can be implemented cleanly in this stack.


## Read First

Before starting, read:

1. `AGENTS.md`
2. `docs/PRD.md`
3. `docs/ARCHITECTURE.md`
4. `features/INDEX.md`
5. `features/_TEMPLATE.md`


## Inputs

Typical inputs:
- a raw feature idea from the user
- an MVP idea from the PRD
- a requested enhancement to an existing feature
- a gap identified in architecture or implementation


## Required Output

Create or update exactly one feature spec in:

`features/PROJ-<id>-<feature-name>.md`

Also update:

`features/INDEX.md`

The feature spec must follow the repository template and be specific enough for architecture and implementation work.


## Requirements Rules

### General
- Do not write vague feature specs.
- Do not write implementation code.
- Do not skip acceptance criteria.
- Do not create duplicate features if similar scope already exists.

### Frontend-aware requirements
When the feature affects UI:
- think in terms of **Next.js App Router routes, pages, layouts, and components**
- assume UI is built with **Tailwind CSS** and **shadcn/ui**
- prefer reuse of existing `src/components/ui/` primitives
- specify loading, empty, success, and error states where relevant

### Backend-aware requirements
When backend is needed:
- assume **Supabase** is the preferred backend platform
- think in terms of **PostgreSQL data**, **auth**, **storage**, **realtime**, and **RLS**
- specify validation expectations clearly and assume **Zod** at runtime boundaries
- capture security and authorization expectations explicitly

### Security-aware requirements
Always consider:
- authentication requirements
- authorization requirements
- data exposure risks
- secret handling boundaries
- abuse cases and misuse scenarios when relevant


## Process

### 1. Review existing feature inventory
Read `features/INDEX.md` first.
Check whether the requested scope already exists or overlaps with an existing feature.

### 2. Determine feature shape
Identify:
- user problem
- target user
- primary flow
- UI impact
- backend impact
- security impact
- deployment relevance

### 3. Create a stack-aware feature spec
Write the spec using `features/_TEMPLATE.md`.

Be explicit about:
- affected routes or screens
- required components
- whether existing shadcn/ui primitives can be reused
- whether Supabase / database / auth / storage / realtime are needed
- validation requirements with Zod
- acceptance criteria that can actually be tested

### 4. Update feature tracking
Add or update the feature in `features/INDEX.md`.

Use a real status such as:
- Draft
- Planned
- In Progress
- Review
- Done


## Output Quality Bar

A good feature spec in this repository:
- is understandable by PM and developer
- is implementation-ready
- is aligned with the actual stack
- does not invent alternative technologies
- makes frontend, backend, and security implications visible


## Do Not

- do not propose unrelated frameworks
- do not suggest alternative UI libraries instead of shadcn/ui
- do not suggest a different ORM / backend platform unless explicitly required
- do not omit validation or authorization requirements when relevant
