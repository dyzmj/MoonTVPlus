---
name: feature-development-multifile
description: Workflow command scaffold for feature-development-multifile in MoonTVPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-multifile

Use this workflow when working on **feature-development-multifile** in `MoonTVPlus`.

## Goal

Implements a new feature or significant enhancement, often involving multiple files across API routes, components, libraries, and configuration.

## Common Files

- `src/app/api/*/route.ts`
- `src/app/[feature]/**/page.tsx`
- `src/components/**.tsx`
- `src/lib/**.ts`
- `src/lib/**.types.ts`
- `src/lib/config.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update API route files under src/app/api/...
- Update or add relevant component files under src/components/ or src/app/[feature]/page.tsx
- Update or add supporting library files under src/lib/
- Update configuration files if needed (e.g., src/lib/config.ts)
- Update types if needed (e.g., src/lib/[feature].types.ts)

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.