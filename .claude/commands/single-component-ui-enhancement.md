---
name: single-component-ui-enhancement
description: Workflow command scaffold for single-component-ui-enhancement in MoonTVPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /single-component-ui-enhancement

Use this workflow when working on **single-component-ui-enhancement** in `MoonTVPlus`.

## Goal

Makes a UI improvement or bugfix to a single component or page, such as adding tooltips, changing layouts, or fixing display issues.

## Common Files

- `src/components/*.tsx`
- `src/app/*/page.tsx`
- `src/app/globals.css`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit the relevant component or page file under src/components/ or src/app/[feature]/page.tsx
- Optionally update related CSS or layout files

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.