# Phase 6 – Frontend

**Read first (and nothing else):** docs/PROGRESS.md, AGENTS.md, docs/specs/SPEC_FRONTEND.md, spec of API from /api OpenAPI

## Goal
A usable web app for the whole user journey.

## Build
- Next.js + TypeScript: landing, docs, auth, dashboard, calendar, live viewer with timing tower and event feed, replay viewer, leaderboard, profiles, admin basics.
- WebSocket client with interpolation and resync handling.
- Accessibility, responsive layout, light/dark.

## Acceptance criteria (prove each with evidence)
- A non-technical user can sign up, upload the starter bot, enter a race and watch it live.
- Replay seek/speed works.
- e2e test (Playwright) covers the main journey.

## Do NOT
Change backend contracts without updating the spec and tests.

## Before you finish
Update docs/PROGRESS.md and docs/DECISIONS.md. Answer using the 8-part response format in AGENTS.md. Then tell me whether to continue in this session or start a fresh one.
