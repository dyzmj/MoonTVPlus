---
name: admin-settings-enhancement
description: Workflow command scaffold for admin-settings-enhancement in MoonTVPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /admin-settings-enhancement

Use this workflow when working on **admin-settings-enhancement** in `MoonTVPlus`.

## Goal

Adds or updates admin-related features, often touching the admin page, related API routes, and configuration/types.

## Common Files

- `src/app/admin/page.tsx`
- `src/app/api/admin/**/route.ts`
- `src/lib/admin.types.ts`
- `src/lib/config.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit src/app/admin/page.tsx
- Create or update related API route files under src/app/api/admin/...
- Update supporting types/configuration files under src/lib/

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.