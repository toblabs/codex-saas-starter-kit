---
name: architecture
description: Create or update the technical design for a feature or system area in this repository
---

# Architecture

## Purpose

Use this skill to create or update the technical design for a feature or system area in this repository.

Architecture in this project must align with the repository defaults:

- **Next.js 16 App Router**
- **TypeScript**
- **Tailwind CSS**
- **shadcn/ui**
- **Supabase**
- **PostgreSQL**
- **Zod**
- **Vercel**

This skill should produce a **high-value technical design**, not vague generalities and not final code.


## Read First

Before starting, read:

1. `AGENTS.md`
2. `docs/PRD.md`
3. `docs/ARCHITECTURE.md`
4. `features/INDEX.md`
5. the relevant feature spec
6. relevant existing implementation files, if they already exist


## Inputs

Typical inputs:
- one feature spec
- several related feature specs
- a request to extend `docs/ARCHITECTURE.md`
- a request to refine backend / frontend / data design


## Required Output

Update one or both of:
- `docs/ARCHITECTURE.md`
- the relevant `features/PROJ-<id>-<feature-name>.md`

The result must clearly explain how the feature fits the repository architecture.


## Architecture Rules

### Frontend architecture
Use:
- **Next.js App Router**
- server/client component boundaries where appropriate
- **Tailwind CSS**
- **shadcn/ui** as the base component system

Always consider:
- route structure
- page/layout ownership
- component reuse
- form handling with **react-hook-form** where relevant
- runtime validation with **Zod** where frontend boundaries need it

### Backend architecture
Use:
- **Supabase** when backend or data is needed
- **PostgreSQL** for persistent data
- **Zod** for runtime validation
- RLS considerations where user-scoped data exists

Always consider:
- table/entity design
- read/write flows
- auth and authorization boundaries
- storage / realtime / edge capabilities if needed

### Deployment architecture
Keep decisions compatible with:
- **Vercel**
- environment variable based configuration
- preview / production environments


## Process

### 1. Understand feature intent
Identify:
- what problem the feature solves
- what part is frontend
- what part is backend
- where state and validation belong
- which security boundaries matter

### 2. Map onto the stack
Translate requirements into stack-native decisions:
- route handlers or server actions
- components and route structure
- Supabase tables / policies / storage
- Zod schemas
- Tailwind / shadcn/ui usage

### 3. Design for reuse
Before proposing new abstractions:
- check whether existing components, hooks, helpers, or data patterns already exist
- prefer extension over replacement

### 4. Record tradeoffs
Where there is more than one valid design, state the chosen approach and why it fits this repository.


## Output Quality Bar

A good architecture output:
- is specific enough for implementation
- names the real stack and its implications
- clarifies frontend/backend boundaries
- addresses auth, validation, and data access
- remains concise and reviewable


## Do Not

- do not produce generic architecture text disconnected from the repo
- do not invent a different deployment target
- do not swap out shadcn/ui, Tailwind, Supabase, or Zod without explicit instruction
- do not hide important auth or RLS implications
