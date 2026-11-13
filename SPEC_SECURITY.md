# Security & sandbox spec
**Threat model**: sandbox escape, reading others' code, network exfiltration, DoS (infinite loop, memory/fork bomb), timing side channels, multi-account leaderboard poisoning, malware uploads, API abuse.
**Layers**
- Upload: authenticated, rate-limited, size-capped, content-type checked, virus scanned, random IDs, immutable (new upload = new version).
- Validation: unpack in throwaway sandbox, verify manifest + contract version, load model, smoke race vs reference bots, measure latency/memory, return human-readable rejection.
- Execution: one container per agent; no network; read-only root FS; no host mounts; non-root; dropped capabilities; seccomp allow-list; cgroups (CPU/mem/PIDs); wall-clock kill; gVisor (later Firecracker). ONNX-only may run in-process in restricted runtime at first.
- Channel: narrow stdin/stdout or Unix socket, fixed binary schema, validate every message, drop malformed.
- Accounting: measure CPU time per tick, not just wall time.
- Secrets: sandboxes never get credentials; services use short-lived scoped tokens.
- Audit: append-only log for submissions, validations, entries, admin actions.
- Abuse: quotas, email verification, OAuth, CAPTCHA, ban + quarantine.
Write `/docs/SECURITY.md` explaining each layer and residual risk. Hostile test bots required: infinite loop, memory bomb, fork bomb, network call, file read, malformed output, timing probe.
