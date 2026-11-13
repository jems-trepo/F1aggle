# AI F1 League – Core Context (always loaded, keep short)

## What we are building
A platform where F1 fans and AI/ML students train a **driver agent**, upload it before a scheduled race, and all agents race in ONE shared deterministic simulation. Viewers watch live positions/gaps/laps; results feed leaderboards and a season championship.
Personas: ML student (trains locally, uploads model), F1 enthusiast (tweaks starter bot/low-code), viewer (watches, no account), admin (schedules, moderates).

## Non-negotiable principles
1. **Determinism**: same track + setups + agents + seed = identical result, bit for bit.
2. **Fairness**: same physics and same egocentric observations for all; fixed per-tick compute budget.
3. **Isolation**: uploaded code is hostile; runs only in the sandbox (no network, read-only FS, cgroup limits, kill timer).
4. **Sim is headless**; viewer only renders streamed state.
5. **One engine everywhere**: local training env, CI and production use the same sim core + version.
6. **Versioned contracts**: obs/action schema, physics, tracks. Races record versions used.
7. **Fail safe**: crashed/slow agent gets a safe default action and a flag; race always finishes.
8. **Observable**: logs/metrics/traces keyed by race_id and submission_id.

## Repo layout
/sim  /sdk  /api  /runner  /web  /infra  /spec  /docs  /prompts

## How you must work (context hygiene – important)
- Work on ONE phase at a time. Read `docs/PROGRESS.md` first, then the current `prompts/phase-N-*.md`, then ONLY the spec files that phase lists under "Read first". Do not load other specs.
- Never paste whole files back into chat. Reference paths and line ranges.
- Plan first (short), then implement in small commits with tests.
- If you are unsure of a library API or version, check the docs; never invent.
- Ask me when blocked or when a decision touches security, cost or the data model. Offer a recommended default.
- Record each decision in `docs/DECISIONS.md` (date, decision, alternatives, reason).
- At the end of a phase, update `docs/PROGRESS.md` (done / not done / next / gotchas). That file is your memory across sessions.
- If the conversation gets long or you notice you are repeating yourself or forgetting earlier rules: STOP, update PROGRESS.md, and tell me to start a fresh session.
- I am learning: explain what you built and how to run/debug it in plain language.

## Tech defaults (confirm in Phase 0)
Python 3.12 + NumPy sim, Gymnasium SDK, FastAPI + SQLAlchemy/Alembic + Postgres + Redis + S3/MinIO, Docker + gVisor sandbox, ONNX Runtime, Next.js + TypeScript, OpenTelemetry/Prometheus/Grafana/Sentry, GitHub Actions, Terraform.

## Response format for every phase
1 Plan · 2 Implementation (paths) · 3 Tests + command · 4 How to run (beginner exact commands) · 5 Acceptance checklist pass/fail with evidence · 6 Risks/open questions · 7 Docs updated · 8 Next phase preview.
