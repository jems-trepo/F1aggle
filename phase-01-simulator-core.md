# Phase 1 – Simulator core (single car)

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_SIM.md

## Goal
A deterministic single-car simulator on one track with a starter bot.

## Build
- Fixed-tick physics, seeded PRNG, track JSON loader (versioned) with one track.
- Car model v1: engine/drag, brake, friction-circle grip.
- Rule-based starter bot (follow centerline, brake before corners).
- Minimal visualiser (matplotlib or terminal) to eyeball a lap.
- Tests: determinism (100 runs identical), no NaN, no wall tunnelling, plausible lap time.

## Acceptance criteria (prove each with evidence)
- Same seed → identical results across 100 runs.
- Lap time is plausible and documented.
- All tests pass in CI.

## Do NOT
Add multiple cars, networking, databases or any web code.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
