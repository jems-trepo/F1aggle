# AI F1 League – Prompt Pack (split to avoid context rot)

## Why it is split
One giant prompt makes the agent forget details as the chat grows. This pack keeps a SMALL always-on core (`AGENTS.md`), loads detailed specs only when a phase needs them, and stores memory in files (`docs/PROGRESS.md`), not in the chat.

## Setup (5 minutes)
1. Create an empty git repo and unzip this pack into its root.
2. `AGENTS.md` is already copied to `.github/copilot-instructions.md` (Copilot) and `CLAUDE.md` (Claude Code). For Cursor, copy it to `.cursor/rules/core.mdc`.
3. Commit: `git add . && git commit -m "Add prompt pack"`.

## Run a phase (copy-paste this)
> Read AGENTS.md and docs/PROGRESS.md. Then follow prompts/phase-00-foundations.md exactly. Load only the files it lists. Use the response format from AGENTS.md.

Change the phase file name each time (phase-01…phase-08). Phase 0 starts by asking YOU questions – answer them.

## Golden rules
- **One phase = one fresh chat session.** Start a new chat for each phase.
- **If a phase runs long** (many files, lots of back and forth), say: "Stop. Update docs/PROGRESS.md with everything needed to continue, then I will start a new session."
- **Resume prompt** for a new session mid-phase:
  > Read AGENTS.md, docs/PROGRESS.md and prompts/phase-N-….md. Continue exactly where PROGRESS.md says. Do not redo finished work.
- **Drift fix** if the agent ignores a rule:
  > Re-read AGENTS.md section "Non-negotiable principles" and fix your last change to comply.
- **Verify yourself**: run the tests and the "How to run" commands before moving on. Tag the commit: `git tag phase-N-done`.
- **Size rule**: ask for ≤ ~10 files changed per request. Big requests = rot and bugs.
- **Review security work** (Phases 3, 4, 7) yourself or with a second review prompt: "Act as an attacker and try to break what you just built; list attacks and test them."

## Order
00 Foundations → 01 Simulator core → 02 Multi-car + contract → 03 Runner + sandbox → 04 Backend → 05 Orchestrator + streaming → 06 Frontend → 07 Production hardening → 08 Advanced.

## Files
- `AGENTS.md` – core context (always loaded)
- `docs/specs/*` – detailed specs loaded per phase
- `prompts/phase-*.md` – one task prompt per phase
- `docs/PROGRESS.md`, `docs/DECISIONS.md` – the agent's memory

Reminder: nothing is truly unbreakable. The design is defense in depth and every layer is tested with hostile bots.
