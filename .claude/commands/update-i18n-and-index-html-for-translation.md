---
name: update-i18n-and-index-html-for-translation
description: Workflow command scaffold for update-i18n-and-index-html-for-translation in SillyTavern.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-i18n-and-index-html-for-translation

Use this workflow when working on **update-i18n-and-index-html-for-translation** in `SillyTavern`.

## Goal

Adds or updates translations, especially Russian, by modifying the i18n.json and corresponding UI in index.html.

## Common Files

- `public/i18n.json`
- `public/index.html`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit public/i18n.json to add or update translation keys/values.
- Edit public/index.html to ensure UI elements are compatible with translations or to fix translation-related display issues.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.