# Ownership Skill

A skill for taking autonomous ownership of a KPI in a codebase. Invoke with `/own <kpi-name> [description]`.

## Structure
- `.claude/commands/own.md` — The skill prompt
- `.ownership/<kpi>/` — Per-KPI state (created by the skill on first run)

## How It Works
1. User invokes `/own <kpi-name> [description]`
2. First run: explores codebase, deliberates on ownership definition, presents to user, starts working
3. Subsequent runs: re-orients from persisted state, continues work
4. Push-based: runs autonomously. Only the user decides when ownership is done.

## First Target
- **Project**: gz-chat-juridisch (`~/projects/gz-chat-juridisch/`)
- **KPI**: Answer trustworthiness — how much should a user trust the legal citations and reasoning the AI provides? Not citation correctness alone, but whether the combination of sources actually supports the conclusion, with appropriate hedging and awareness of limitations.

