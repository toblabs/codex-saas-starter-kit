---
name: backend
description: Implement or refine backend functionality for this repository
---

# Backend

## Purpose

Use this skill to implement or refine backend functionality for this repository.

Backend work in this project should be designed around:

- **Supabase**
- **PostgreSQL**
- **Zod**
- **Vercel-compatible application design**

When backend is not needed, do not invent it.  
When backend is needed, keep it aligned with the repository defaults.


## Read First

Before starting, read:

1. `AGENTS.md`
2. `docs/PRD.md`
3. `docs/ARCHITECTURE.md`
4. `features/INDEX.md`
5. the relevant feature spec
6. relevant existing backend/data files


## Backend Rules

### Technology rules
- Prefer **Supabase** for backend capabilities
- Prefer **PostgreSQL** data modeling
- Prefer **Zod** for runtime validation
- Keep architecture compatible with **Vercel**

### Data rules
- Keep schema changes explicit
- think in entities, relationships, indexes, and access patterns
- document migrations or schema impact where relevant

### Auth and security rules
- consider authentication and authorization explicitly
- use RLS thinking where user-owned data exists
- do not hardcode secrets
- do not blur public and protected operations

### API / server rules
- use existing repository patterns for route handlers / server actions / server-side helpers
- validate input and output boundaries
- fail safely and explicitly


## Process

### 1. Confirm backend need
Check whether the feature actually needs:
- database changes
- auth changes
- storage
- realtime
- protected server logic

### 2. Inspect current backend patterns
Look for:
- current Supabase helpers
- schema conventions
- existing validation patterns
- existing auth and access approaches

### 3. Design data and access
Clarify:
- entities or tables
- who can read and write
- what validation is required
- what failure modes matter

### 4. Implement minimal safe change
Prefer:
- explicit validation
- explicit authorization
- minimal schema surface
- reviewable code over magic

### 5. Sync documentation
Update architecture or feature docs when backend scope materially changes.


## Output Quality Bar

A good backend change:
- fits Supabase/PostgreSQL cleanly
- uses Zod where runtime validation matters
- considers auth and RLS
- avoids unnecessary complexity
- is safe for deployment


## Do Not

- do not switch to a different backend stack without explicit instruction
- do not leave authorization implicit
- do not ignore validation
- do not hardcode environment-dependent values
