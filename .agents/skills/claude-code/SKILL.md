```markdown
# claude-code Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill documents the core development patterns and workflows for the `claude-code` repository. The project is written in TypeScript, with no specific framework detected. It follows clear conventions for file naming, import/export styles, commit messages, and includes a workflow for maintaining production readiness documentation.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.

  **Example:**
  ```
  user_profile.ts
  api_utils.ts
  ```

### Import Style
- Use **relative imports** for referencing modules within the project.

  **Example:**
  ```typescript
  import { fetch_data } from './api_utils';
  ```

### Export Style
- Use **named exports** for all exported functions, types, or constants.

  **Example:**
  ```typescript
  // In api_utils.ts
  export function fetch_data(url: string): Promise<any> {
    // ...
  }
  ```

### Commit Messages
- Use **conventional commit** format, primarily with the `chore` prefix.
- Keep commit messages concise (~62 characters on average).

  **Example:**
  ```
  chore: update production readiness documentation
  ```

## Workflows

### Add Production Readiness Control
**Trigger:** When introducing or updating production readiness standards or documentation.  
**Command:** `/add-production-readiness-docs`

1. Edit or create production readiness documentation in relevant markdown files (e.g., `AGENTS.md`, `CLAUDE.md`).
2. Add or update centralized production readiness files in the `.github` directory (e.g., `PRODUCTION_READINESS.md`, `pull_request_template.md`).
3. Commit each file change with a descriptive message referencing production readiness.

**Files Involved:**
- `AGENTS.md`
- `CLAUDE.md`
- `.github/PRODUCTION_READINESS.md`
- `.github/pull_request_template.md`

**Example Commit:**
```
chore: add production readiness checklist to PRODUCTION_READINESS.md
```

## Testing Patterns

- Test files use the pattern `*.test.*` (e.g., `api_utils.test.ts`).
- The specific testing framework is not detected, but tests are colocated with source files or in parallel structure.
- To write a test, create a file named with `.test.` before the extension.

  **Example:**
  ```
  // api_utils.test.ts
  import { fetch_data } from './api_utils';

  test('fetch_data returns expected result', async () => {
    const result = await fetch_data('https://api.example.com/data');
    expect(result).toBeDefined();
  });
  ```

## Commands

| Command                        | Purpose                                                        |
|--------------------------------|----------------------------------------------------------------|
| /add-production-readiness-docs | Add or update production readiness documentation and controls.  |
```
