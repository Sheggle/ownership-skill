# Ownership Skill

A skill for taking autonomous ownership of a KPI in a codebase. Invoke with `/own <kpi-name> [description]`.

## Structure
- `.claude/commands/own.md` — The skill prompt
- `prompts/` — Deliberation agent prompts (challenger, guardian, strategist)
- `target/` — The target codebase (currently: gz-chat-juridisch)
- `.ownership/<kpi>/` — Per-KPI state (created by the skill on first run)

## How It Works
1. User invokes `/own <kpi-name> [description]`
2. First run: explores codebase, deliberates on ownership definition, presents to user, starts working
3. Subsequent runs: re-orients from persisted state, continues work
4. Push-based: runs autonomously. Only the user decides when ownership is done.

## Deliberation Protocol
Before significant decisions, the owner spawns three agents:
- **Challenger**: finds flaws in the approach
- **Guardian**: checks for collateral damage to the rest of the system
- **Strategist**: evaluates whether the action serves the KPI or is busywork

Deliberation output is always logged in the decision log.

## Target: gz-chat-juridisch
A Dutch legal consultation chat app. FastAPI + SQLite FTS5 (1.1M legal documents) + Claude integration + E2E encryption. See `target/` for the full codebase.
