# Orchestrator + streaming spec
States: SCHEDULED → ENTRIES_OPEN → ENTRIES_LOCKED → QUALIFYING → GRID_SET → RUNNING → FINISHED → VERIFIED → PUBLISHED (+ CANCELLED, FAILED). Each transition idempotent and recorded; crash/restart resumes safely.
- At ENTRIES_LOCKED pin each entrant's latest approved submission + setup.
- Race seed generated and stored (or committed in advance, revealed later).
- Runner publishes state to stream gateway AND writes replay (compressed keyframes + deltas).
- Verifier re-simulates from replay inputs; only identical results get published and score points.
- Scheduling: cron-like recurring races, UTC storage, local-time countdowns.
**Streaming**: WebSocket per race channel; initial snapshot then deltas at 10–20 Hz; clients interpolate; sequence numbers + resync request; versioned schema; late join; replays served from stored files; pub/sub fan-out; slow clients dropped/downsampled; public read-only spectating with IP rate limits.
