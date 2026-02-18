# Claude Code Project Template

Reusable `CLAUDE.md` template for [Claude Code](https://claude.com/claude-code) projects.

Includes TDD workflow, three-layer doc hierarchy, plans lifecycle, and requirement archiving rules.

## Quick Start

```bash
# 1. Download template as CLAUDE.md
curl -fsSL https://raw.githubusercontent.com/samque1983/claude-template/main/CLAUDE_TEMPLATE.md -o CLAUDE.md

# 2. Create directory structure
mkdir -p req docs/specs docs/plans archive

# 3. Create the constitution file
touch req/GLOBAL_MASTER.md
```

## Customize

Open `CLAUDE.md` and fill in the `<!-- -->` placeholders:

| Section | What to fill |
|---------|-------------|
| `<PROJECT_NAME>` | Your project name |
| **Mirror Testing Rule** | Source file → test file mappings |
| **Spec-to-Code Mapping** | `docs/specs/*.md` → source module mappings |
| **UI Standard** | Design system reference (if applicable) |
| **Architecture Rules** | Import direction, data exchange format, config authority |

## What's Included

- **TDD Core** — Red → Green → Refactor, enforced on every task
- **Mirror Testing** — Every source file has a corresponding test file
- **Three-Layer Doc Hierarchy** — `req/` (WHAT) → `docs/specs/` (HOW) → `docs/plans/` (temporary)
- **Plans Workflow** — Plans guide implementation, then get deleted when specs are synced
- **Requirement Lifecycle** — Active in `req/`, archived to `archive/` when done
- **Source of Truth** — `docs/specs/` is authoritative after implementation, not requirements

## Directory Structure

```
your-project/
├── CLAUDE.md              ← Workflow rules (always loaded by Claude Code)
├── req/
│   ├── GLOBAL_MASTER.md   ← Universal constraints (never archive)
│   └── PHASE_N_*.md       ← Feature requirements (archive when done)
├── docs/
│   ├── specs/             ← Design specs, 1:1 with source modules (permanent)
│   └── plans/             ← Working docs during implementation (delete when done)
├── archive/               ← Completed phase requirements
└── tests/                 ← Mirror test files
```
