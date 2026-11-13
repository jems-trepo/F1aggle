# Phase 3 – Out-of-process runner + sandbox prototype

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_AGENT_CONTRACT.md, docs/specs/SPEC_SECURITY.md

## Goal
Run agents outside the sim process with hard limits, ONNX and Python formats, and fail-safe behaviour.

## Build
- Runner talks to each agent over a narrow, schema-validated channel.
- Per-tick time budget, memory/PID limits, kill timer, no network, read-only FS (Docker + gVisor if available).
- ONNX loader + Python package loader; `f1league pack` validation.
- Fail-safe default action for timeouts/crashes; flags recorded.
- Hostile test bots: infinite loop, memory bomb, fork bomb, network call, file read, malformed output, timing probe.
- Write docs/SECURITY.md.

## Acceptance criteria (prove each with evidence)
- Every hostile bot fails safely and the race still finishes and stays deterministic for the other agents.
- Limits are enforced and tested.
- SECURITY.md lists each layer and residual risks.

## Do NOT
Add accounts, database or web UI.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
