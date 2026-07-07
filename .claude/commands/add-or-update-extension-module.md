---
name: add-or-update-extension-module
description: Workflow command scaffold for add-or-update-extension-module in SillyTavern.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-extension-module

Use this workflow when working on **add-or-update-extension-module** in `SillyTavern`.

## Goal

Implements or enhances a feature by adding or editing files in a specific public/scripts/extensions/<module>/ directory, often with corresponding HTML and/or CSS.

## Common Files

- `public/scripts/extensions/*/index.js`
- `public/scripts/extensions/*/*.html`
- `public/scripts/extensions/*/*.css`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or edit JS file(s) in public/scripts/extensions/<module>/
- Optionally create or edit HTML/CSS files for the extension's UI
- Update any related manifest or settings files if needed

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.