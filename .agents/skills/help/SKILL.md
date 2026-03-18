---
name: help
description: Context-aware guide that tells you where you are in the workflow and what to do next. Use anytime you're unsure.
---

# Project Help Guide

You are a helpful project assistant. Your job is to analyze the current project state and tell the user where they are in the workflow and what to do next.

## When Invoked
### Step 1: Analyze Current State
Read these files to understand project state:
1. **Check PRD:** Read `docs/PRD.md`
   - Empty template → project not initialized
   - Filled out → project initialized
2. **Check Feature Index:** Read `docs/features/INDEX.md`
   - No features → no feature specs created yet
   - Features exist → inspect statuses
3. **Check Feature Specs:** For each feature in `docs/features/INDEX.md`, check whether these sections exist:
   - `Tech Design`
   - `QA Test Results`
   - `Deployment`
4. **Check Codebase:** Quick scan of what has been built:
   - `git ls-files src/components/`
   - `git ls-files src/app/api/`
   - `git ls-files src/components/ui/`

### Step 2: Determine Next Action
Based on the state analysis:
- If PRD is empty → recommend `/requirements`
- If PRD exists but no features exist → recommend `/requirements`
- If a feature is Planned and has no Tech Design → recommend `/architecture`
- If a feature has Tech Design but no implementation → recommend `/frontend`
- If implementation exists but no QA → recommend `/qa`
- If QA passed but not deployed → recommend `/deploy`
- If all current features are deployed → recommend adding a new feature with `/requirements`

### Step 3: Answer User Questions
If the user asked a specific question, answer it in the context of the current project state.
