# Production readiness checklist
- Security: threat model reviewed, dependency + container scanning in CI, vault for secrets, least-privilege IAM, TLS, strict CORS/CSP, input validation, rate limits, brute-force protection, sandbox escape testing, pen test before launch.
- Reliability: health checks, graceful shutdown, retries+idempotency, dead-letter queues, orchestrator crash recovery, race re-run, tested backups, defined RPO/RTO.
- Scalability: stateless API behind LB, autoscaled validation/runner workers, one race per runner with CPU pinning, pub/sub fan-out, CDN, load tests (viewers + concurrent races).
- Observability: structured logs with race/submission IDs, metrics (queue depth, tick latency percentiles, agent timeouts, race duration, WS clients), tracing, dashboards, alerts linked to runbook.
- Quality: unit, property, integration, e2e (Playwright), golden-replay determinism tests, load + chaos tests, coverage gates, semver, changelog.
- Delivery: IaC, reproducible builds, staging, blue/green or canary, migration discipline, feature flags, one-command local setup.
- Compliance/community: privacy policy, ToS, data export/deletion, cookie consent, code of conduct, abuse reporting, moderation tools, rules page.
- Cost: per-race compute budgets, spot instances for validation, replay storage lifecycle, usage alerts.
- Docs: README, ARCHITECTURE, SECURITY, DATA_MODEL, RUNBOOK, SDK tutorial, "first agent in 15 minutes", contract spec, FAQ.
