```markdown
# SillyTavern Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and common workflows used in the SillyTavern repository. SillyTavern is a JavaScript project using the Express framework, with a modular frontend and backend structure. The codebase emphasizes maintainable file organization, clear commit practices, and streamlined workflows for translation, extension development, dependency management, and backend API evolution.

## Coding Conventions

### File Naming
- **PascalCase** is used for file names.
  - Example: `MyComponent.js`, `UserProfile.js`

### Import Style
- **Relative imports** are used throughout the codebase.
  - Example:
    ```js
    import { fetchData } from '../utils/DataFetcher.js';
    ```

### Export Style
- **Named exports** are preferred.
  - Example:
    ```js
    // In UserProfile.js
    export function renderProfile(user) { ... }
    export const PROFILE_TYPE = 'user';
    ```

### Commit Patterns
- Commit messages are freeform, sometimes with prefixes, averaging 39 characters.

## Workflows

### Update i18n and index.html for Translation
**Trigger:** When you want to add or improve language translations in the UI.  
**Command:** `/add-translation`

1. Edit `public/i18n.json` to add or update translation keys/values.
    ```json
    {
      "greeting": {
        "en": "Hello",
        "ru": "Привет"
      }
    }
    ```
2. Edit `public/index.html` to ensure UI elements are compatible with translations or to fix translation-related display issues.
    ```html
    <span data-i18n="greeting"></span>
    ```

---

### Add or Update Extension Module
**Trigger:** When you want to add a new extension or improve an existing extension's functionality.  
**Command:** `/add-extension`

1. Create or edit JS file(s) in `public/scripts/extensions/<module>/`.
    ```js
    // public/scripts/extensions/myExtension/index.js
    export function initExtension() { ... }
    ```
2. Optionally create or edit HTML/CSS files for the extension's UI.
    ```html
    <!-- public/scripts/extensions/myExtension/ui.html -->
    <div class="my-extension-panel"></div>
    ```
    ```css
    /* public/scripts/extensions/myExtension/style.css */
    .my-extension-panel { ... }
    ```
3. Update any related manifest or settings files if needed.

---

### Update Package Dependencies
**Trigger:** When you want to update or add a package dependency.  
**Command:** `/update-deps`

1. Edit `package.json` to update/add/remove dependencies.
    ```json
    "dependencies": {
      "express": "^4.18.2",
      "new-package": "^1.0.0"
    }
    ```
2. Regenerate `package-lock.json` to lock versions.
    ```sh
    npm install
    ```

---

### Add or Update Backend Endpoint
**Trigger:** When you want to add a new backend feature or fix an API bug.  
**Command:** `/add-endpoint`

1. Edit or create JS files in `src/endpoints/backends/` or `src/endpoints/`.
    ```js
    // src/endpoints/backends/myApi.js
    export function myApiHandler(req, res) { ... }
    ```
2. Optionally update related frontend files if new data/fields are exposed.

---

### Merge Release or Staging into Feature Branch
**Trigger:** When you want to update your feature branch with the latest upstream changes.  
**Command:** `/merge-upstream`

1. Merge release or staging branch into the current feature branch.
    ```sh
    git checkout my-feature
    git merge release
    ```
2. Resolve any merge conflicts.
3. Update affected files as needed.

---

## Testing Patterns

- **Framework:** Unknown (not explicitly detected)
- **File Pattern:** Test files follow the `*.test.*` naming convention.
    - Example: `UserProfile.test.js`
- **Typical Test Structure:**  
  While the specific framework is not identified, tests are likely to use standard JavaScript testing libraries (e.g., Jest, Mocha) and are placed alongside or near the modules they test.

## Commands

| Command           | Purpose                                                        |
|-------------------|----------------------------------------------------------------|
| /add-translation  | Add or update translations in i18n and UI                      |
| /add-extension    | Create or enhance an extension module                          |
| /update-deps      | Update or add npm package dependencies                        |
| /add-endpoint     | Add or modify backend API endpoints                            |
| /merge-upstream   | Merge release/staging into your feature branch                 |
```