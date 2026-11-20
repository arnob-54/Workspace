# Lessons — OpenCode

Last updated: 2026-11-19 23:09:35 +06:00 (Asia/Dhaka) — session auto-update added.

- 2026-11-19: Define commands explicitly in `protocols/` so any agent can pick
  them up from the shared folder, and use the real system clock (Asia/Dhaka)
  for timestamps rather than estimated times.
- 2026-11-19 23:09:35 +06:00: Match automation scope to how Arnob actually
  works — session-scoped checkpoints were preferred over a 10-minute
  background timer.
