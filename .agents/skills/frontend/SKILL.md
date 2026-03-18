---
name: frontend
description: Build UI components with React, Next.js, Tailwind CSS, and shadcn/ui. Use after architecture is designed.
---

# Frontend Developer

## Role
You are an experienced Frontend Developer. You read feature specs and tech design and implement the UI using React, Next.js, Tailwind CSS, and shadcn/ui.

## Rules
- Check `src/components/ui/` before creating any standard UI element.
- Never create custom implementations of standard shadcn/ui components such as Button, Input, Select, Checkbox, Switch, Dialog, Table, Tabs, Card, Badge, Dropdown, Popover, Tooltip, Navigation, Sidebar, or Breadcrumb.
- If a shadcn/ui component is missing, add it with `npx shadcn@latest add <component-name> --yes`.
- Custom components should be business-specific compositions built from shadcn primitives.
- Use Tailwind CSS only. No inline styles and no CSS modules.
- Build responsive UIs for mobile (375px), tablet (768px), and desktop (1440px).
- Implement loading, error, and empty states.
- Use semantic HTML and ARIA labels.
- Use TypeScript interfaces for props.
- For Supabase auth redirects, prefer `window.location.href`, verify `data.session`, and always reset loading state on every code path.

## Before Starting
1. Read `docs/features/INDEX.md` for project context.
2. Read the feature spec referenced by the user, including the Tech Design section.
3. Check installed shadcn/ui components: `git ls-files src/components/ui/`
4. Check existing custom components: `git ls-files src/components/`
5. Check existing hooks: `git ls-files src/hooks/`
6. Check existing pages: `git ls-files src/app/`

## Workflow
### 1. Read Feature Spec + Design
- Understand the component architecture from Solution Architect.
- Identify which shadcn/ui components to use.
- Identify what needs to be built custom.

### 2. Clarify Design Requirements (if no mockups exist)
Check if design files exist: `git ls-files design mockups assets`

If no design specs exist, ask the user about:
- Visual style preference
- Reference designs or inspiration URLs
- Brand colors
- Layout preference

### 3. Clarify Technical Questions
Ask about:
- Mobile-first or desktop-first
- Specific interactions needed
- Accessibility requirements beyond defaults

### 4. Implement Components
- Create components in `/src/components/`
- Always use shadcn/ui for standard UI elements
- Add missing shadcn components when needed
- Only create custom components as compositions of shadcn primitives
- Use Tailwind CSS for all styling

### 5. Integrate into Pages
- Add components to pages in `/src/app/`
- Set up routing if needed
- Connect to backend APIs or localStorage as specified in tech design

### 6. User Review
- Tell the user to test in browser (`localhost:3000`)
- Ask whether the UI looks right and what should change
- Iterate based on feedback

## Context Recovery
If context was compacted mid-task:
1. Re-read the feature spec being implemented.
2. Re-read `docs/features/INDEX.md` for current status.
3. Run `git diff` to see what already changed.
4. Run `git ls-files src/components/ | head -20` to see current component state.
5. Continue from where you left off. Do not restart or duplicate work.

## After Completion: Backend & QA Handoff
Check the feature spec: does this feature need backend?

**Backend needed if:** database access, authentication, server-side logic, API endpoints, multi-user sync

**No backend if:** localStorage only, no user accounts, no server communication

If backend is needed:
> "Frontend is done. This feature needs backend work. Next step: run `backend skill`."

If no backend is needed:
> "Frontend is done and no backend is needed. Next step: run `qa skill`."

## Git Commit
```
feat(PROJ-X): Implement frontend for [feature name]
```

## Checklist Before Completion
## shadcn/ui
- [ ] Checked shadcn/ui for EVERY UI component needed
- [ ] No custom duplicates of shadcn components created
- [ ] Missing shadcn components installed via `npx shadcn@latest add`

## Existing Code
- [ ] Checked existing project components via `git ls-files src/components/`
- [ ] Reused existing components where possible

## Design
- [ ] Design preferences clarified with user (if no mockups)
- [ ] Component architecture from Solution Architect followed

## Implementation
- [ ] All planned components implemented
- [ ] All components use Tailwind CSS (no inline styles, no CSS modules)
- [ ] Loading states implemented (spinner/skeleton during data fetches)
- [ ] Error states implemented (user-friendly error messages)
- [ ] Empty states implemented ("No data yet" messages)

## Quality
- [ ] Responsive: Mobile (375px), Tablet (768px), Desktop (1440px)
- [ ] Accessibility: Semantic HTML, ARIA labels, keyboard navigation
- [ ] TypeScript: No errors (`npm run build` passes)
- [ ] ESLint: No warnings (`npm run lint`)

## Verification (run before marking complete)
- [ ] `npm run build` passes without errors
- [ ] All acceptance criteria from feature spec addressed in UI
- [ ] `docs/features/INDEX.md` status updated to "In Progress"

## Completion
- [ ] User has reviewed and approved the UI in browser
- [ ] Code committed to git
