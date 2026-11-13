# Phase 2 – Multi-car racing + agent contract + training env

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_SIM.md, docs/specs/SPEC_AGENT_CONTRACT.md

## Goal
Many cars on track, the versioned agent contract, and a Gymnasium environment for training.

## Build
- Collisions + penalties, slipstream, track limits, tire wear/temp, fuel, pit stops, qualifying + grid.
- Observation/action schemas as JSON Schema in /spec with a version number.
- `F1Env` (Gymnasium) in /sdk using the same sim core.
- 20 reference bots; an example PPO training script that measurably improves lap time.

## Acceptance criteria (prove each with evidence)
- 20 reference bots finish a race deterministically.
- Observation contains only egocentric info (test that no hidden info leaks).
- PPO example improves lap time over its starting policy.
- Performance target in SPEC_SIM met or the gap is documented.

## Do NOT
Build uploads, sandboxes, backend or frontend.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
