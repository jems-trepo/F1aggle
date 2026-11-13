# Phase 4 – Backend, uploads, validation, data

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_DATA_API_SCORING.md, docs/specs/SPEC_SECURITY.md

## Goal
Auth, database, upload API and validation workers with a clear submission lifecycle.

## Build
- FastAPI app, SQLAlchemy + Alembic migrations for the data model, object storage (MinIO locally).
- Auth (email verification; OAuth if decided in Phase 0).
- POST /submissions with size/type limits, hashing, virus scan hook, immutable versions.
- Validation worker via queue: unpack in sandbox, check manifest/contract, smoke race, return human-readable result.
- Audit log, rate limits, OpenAPI docs, docs/DATA_MODEL.md.

## Acceptance criteria (prove each with evidence)
- Upload → validated → approved works end to end locally via docker-compose.
- Bad uploads give clear rejection reasons.
- Migrations apply cleanly from empty; API tests pass in CI.

## Do NOT
Build the orchestrator, streaming or the frontend.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
