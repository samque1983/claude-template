# Global Agent Behavior

## Autonomous Execution
- Do NOT ask for confirmation before executing. Proceed with the optimal default approach.
- When multiple valid approaches exist, choose the most conventional/standard one and proceed.
- Only ask the user when the task is genuinely ambiguous (multiple fundamentally different interpretations).
- For destructive git operations (force push, reset --hard, branch -D), still confirm with the user.

## Agentic Workflow Standards

### TDD Core
Strictly follow Test-Driven Development for all functional changes.
- Write the failing test FIRST, run it to confirm failure.
- Write the minimum implementation to make it pass.
- Refactor only after green.
- Never mark a task as "Done" until tests show 100% pass rate.

### Execution Protocol
- Before implementation: write test → run test → see RED.
- After implementation: run test → see GREEN (100% pass).
- On commit: all tests must pass.

## Document Hierarchy

Three-layer documentation. Claude reads **CLAUDE.md** automatically; read others **on demand**.

```
CLAUDE.md                  ← Always loaded (base rules)
req/                       ← Requirements (WHAT)
  GLOBAL_MASTER.md           ← Constitution: universal constraints
  PHASE_N_*.md               ← Individual feature requirements
docs/specs/                ← Design specs (HOW), 1:1 mapped to source modules
docs/plans/                ← Temporary working docs (delete after specs synced)
```

### Reading Protocol
- **Before any implementation task:** read `req/GLOBAL_MASTER.md` first.
- **When modifying existing code:** read the corresponding `docs/specs/*.md`.
- **When implementing a new feature:** read `req/GLOBAL_MASTER.md` + relevant `req/PHASE_N_*.md`.
- **Do NOT load all docs at once.** Only read files relevant to the current task.

### Plans Workflow
- Plans are temporary working documents. Specs are the permanent record.
- Naming: `docs/plans/YYYY-MM-DD-<feature-name>-<type>.md`
- Delete plans after specs are synced with code.

### Document Lifecycle

| Document Type | Path | Lifespan | Action When Complete |
|---------------|------|----------|----------------------|
| Constitution | `req/GLOBAL_MASTER.md` | Permanent | Never archive |
| Requirements | `req/PHASE_N_*.md` | Until implemented | Archive to `archive/` |
| Specifications | `docs/specs/*.md` | While code exists | Keep 1:1 with source |
| Plans | `docs/plans/*.md` | During implementation | Delete after specs synced |

### Source of Truth Hierarchy
1. `docs/specs/*.md` — current implementation (authoritative)
2. `req/PHASE_N_*.md` — original intent (may drift)
3. `req/GLOBAL_MASTER.md` — universal constraints
