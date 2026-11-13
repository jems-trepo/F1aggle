# Phase 7 – Production hardening

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_PRODUCTION.md, docs/specs/SPEC_SECURITY.md

## Goal
Make it safe, observable, scalable and recoverable.

## Build
Work through SPEC_PRODUCTION.md as a checklist: IaC (Terraform), staging, CI/CD with scanning, secrets in a vault, observability stack and alerts, load + chaos tests, backup/restore drill, rate limits, privacy/ToS pages, RUNBOOK.md, sandbox escape tests, pen-test plan.

## Acceptance criteria (prove each with evidence)
- Every checklist item is ticked with evidence or consciously deferred in DECISIONS.md.
- Restore from backup practised.
- New developer can run everything locally in under 30 minutes using the docs.

## Do NOT
Add new features.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
