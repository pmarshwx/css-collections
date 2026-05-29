# Project Instructions for AI Agents

This file provides instructions and context for AI coding agents working on this project.

<!-- BEGIN BEADS INTEGRATION v:1 profile:minimal hash:7510c1e2 -->
## Beads Issue Tracker

This project uses **bd (beads)** for issue tracking. Run `bd prime` to see full workflow context and commands.

### Quick Reference

```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --claim  # Claim work
bd close <id>         # Complete work
```

### Rules

- Use `bd` for ALL task tracking — do NOT use TodoWrite, TaskCreate, or markdown TODO lists
- Run `bd prime` for detailed command reference and session close protocol
- Use `bd remember` for persistent knowledge — do NOT use MEMORY.md files

**Architecture in one line:** issues live in a local Dolt DB; sync uses `refs/dolt/data` on your git remote; `.beads/issues.jsonl` is a passive export. See https://github.com/gastownhall/beads/blob/main/docs/SYNC_CONCEPTS.md for details and anti-patterns.

## Session Completion

**When ending a work session**, you MUST complete ALL steps below. Work is NOT complete until `git push` succeeds.

**MANDATORY WORKFLOW:**

1. **File issues for remaining work** - Create issues for anything that needs follow-up
2. **Run quality gates** (if code changed) - Tests, linters, builds
3. **Update issue status** - Close finished work, update in-progress items
4. **PUSH TO REMOTE** - This is MANDATORY:
   ```bash
   git pull --rebase
   git push
   git status  # MUST show "up to date with origin"
   ```
5. **Clean up** - Clear stashes, prune remote branches
6. **Verify** - All changes committed AND pushed
7. **Hand off** - Provide context for next session

**CRITICAL RULES:**
- Work is NOT complete until `git push` succeeds
- NEVER stop before pushing - that leaves work stranded locally
- NEVER say "ready to push when you are" - YOU must push
- If push fails, resolve and retry until it succeeds
<!-- END BEADS INTEGRATION -->


## What This Repo Is

A collection of hand-authored CSS stylesheets used to brand documents and
(eventually) websites with **Oklahoma Baptist University (OBU)** colors:

- **OBU Green** `#295b30`
- **OBU Gold** `#c48b2b`

The current sheet, `obu.css`, styles Markdown preview/export so that Markdown
documents render with OBU branding before being converted to PDF (via the
VS Code "Markdown PDF" / "Markdown Preview" or Marked 2 toolchains).

## Build & Test

There is no build step — these are static `.css` files consumed directly by
the renderer. "Testing" is visual:

1. Point your Markdown previewer/PDF exporter at the stylesheet (e.g. set
   `markdown-pdf.styles` or Marked 2's custom CSS to `obu.css`).
2. Render a representative Markdown document and inspect headings, code blocks,
   tables, blockquotes, `.qa-block` answer areas, and the print/PDF output.

A linter such as `stylelint` may be added later (see beads issues).

## Architecture Overview

- `obu.css` — the OBU-branded Markdown/PDF stylesheet. Self-contained; targets
  the `body` / `.vscode-body` / `.markdown-body` containers used by VS Code and
  Marked 2 previews, plus an `@media print` block for PDF tuning.
- Custom helper classes for printable worksheets live alongside the base
  styles: `.qa-block`, `.answer-space`, `.answer-lines`, `.answer-box`,
  `.page-break`.
- Future website stylesheets will be added at the repo root (flat layout for
  now; revisit folder structure once a second sheet exists).

## Conventions & Patterns

- **Brand colors are literal hex values today.** OBU Green `#295b30` and
  OBU Gold `#c48b2b` are repeated inline. Centralizing them into CSS custom
  properties (`--obu-green`, `--obu-gold`) is tracked in beads — prefer that
  approach for new work.
- **`!important` is intentional** in `obu.css`: preview/PDF tools inject their
  own default stylesheets, so overrides need the extra specificity. Keep using
  it within the Markdown sheet. Website CSS (added later) should NOT rely on
  `!important`.
- Keep print/PDF concerns inside the `@media print` block.
- Two-space indentation, lowercase hex, one selector per line in grouped
  selector lists (matches existing style).
