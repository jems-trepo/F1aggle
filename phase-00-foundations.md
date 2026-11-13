# Phase 0 – Foundations

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, (no specs needed yet)

## Goal
Ask me the setup questions, then create the repo skeleton, tooling and CI.

## Build
1. FIRST ask in ONE message (with recommended defaults): my Python/TypeScript/DevOps experience and installed tools; AI coding tool + OS; local-only or cloud (which, budget); launch scale; ONNX-only vs Python code in v1; OAuth vs anonymous; public vs private event; Python vs Rust sim; branding/domain; legal constraints. Wait for answers.
2. Monorepo: /sim /sdk /api /runner /web /infra /spec /docs.
3. Tooling: formatter, linter, type checker, pre-commit, Makefile/just with one-command setup, docker-compose skeleton.
4. CI skeleton (lint + test) on GitHub Actions.
5. docs/ARCHITECTURE.md with a Mermaid diagram of the components and data flow (Web, API, Postgres, Redis, object storage, validation workers, orchestrator, runner, sandboxes, stream gateway, observability).

## Acceptance criteria (prove each with evidence)
- CI is green on an empty test suite.
- `make setup` works from a clean clone.
- ARCHITECTURE.md renders with the diagram.
- Answers to my questions are recorded in DECISIONS.md.

## Do NOT
Write any simulator or product code yet.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
