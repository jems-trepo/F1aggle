# Phase 5 – Race orchestrator, streaming, replay, verifier

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_ORCHESTRATOR_STREAMING.md, docs/specs/SPEC_DATA_API_SCORING.md

## Goal
A scheduled race that runs unattended, streams live, stores a replay, and is verified.

## Build
- Orchestrator state machine with idempotent, recorded transitions and crash recovery.
- Entry locking, pinned submissions, qualifying, grid, race seed handling.
- Runner publishes snapshots/deltas to Redis pub/sub; WebSocket gateway with sequence numbers and resync.
- Replay writer + verifier (re-simulate and compare).
- Results, points and rating updates.

## Acceptance criteria (prove each with evidence)
- A scheduled race runs start-to-finish with no manual steps.
- Killing the orchestrator mid-race and restarting recovers or fails cleanly.
- Verifier reproduces results exactly; a tampered replay is rejected.

## Do NOT
Polish the UI beyond a simple test client.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
