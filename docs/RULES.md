English | [中文文档](RULES_zh.md)

# Project Rules

## Rule Strength

All rules are **mandatory**. Violation must be reported and blocked.

## Violation Handling

- Report any rule violation to user before proceeding
- When rules conflict, report to user and await decision
- Do not silently ignore or bypass rules

---

## Documentation

### TODO
- Pending tasks only; remove completed items
- Completed items → CHANGELOG or FEATURES

### Multi-language
- All docs in `docs/` must have EN/ZH versions
- Top of file: language switch links

### README
- Bottom: link to FEATURES, CHANGELOG, TODO

### Design Docs
- Delete after implementation complete

### Cleanup
- Only manage files tracked by git
- Never auto-delete untracked files

## Version
- `package.json` is the single source of truth for version
- CHANGELOG versions are historical records only

## Architecture
- Core business logic modules must not import `vscode` module directly
- Use dependency injection; interact with VSCode API via interfaces
- Utility modules must minimize `vscode` dependencies

## Security
- CSP: no `unsafe-inline`
- Styles must be in external CSS files (e.g., `dist/webview.css`)

## i18n (if applicable)
- New UI strings: add keys to all `package.nls.*.json` files
- New keys must be added to all language files simultaneously

## Pre-commit Checks
- `npm run lint` - ESLint must pass
- `npm run build` - Compile must succeed
- `npm test` - Unit tests must pass
- `git status` - Review staged/untracked files

## Git

### Branch Naming
- Format: `<type>/<short-description>`
- Examples: `feature/quota-prediction`, `fix/statusbar-display`, `docs/update-readme`

### Commit Messages (Conventional Commits)
- Format: `<type>: <description>`
- Types: `feat`, `fix`, `refactor`, `docs`, `chore`
