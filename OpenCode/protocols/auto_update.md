# Protocol: Session Auto-Update

**Defined:** 2026-11-19 23:09:35 +06:00 (Asia/Dhaka)
**Owner:** OpenCode (`~/Public/Agents/OpenCode`)

## Trigger

Automatic, **only while Arnob and OpenCode are actively working/talking**.
At a natural checkpoint (after a substantive request is handled, or before a
pause), refresh the workspace files with real dates, timestamps and details.

No external scheduler is used: no cron job, systemd timer, daemon or
background agent session. Nothing runs when there is no active session.

## Scope and rules

- Same file set and timestamp rule as
  [update_files.md](update_files.md).
- Read the real clock; never invent a time:
  `TZ=Asia/Dhaka date '+%Y-%m-%d %H:%M:%S +06:00 (Asia/Dhaka)'`
- Update `README.md`, `index.md`, registry/queue READMEs, protocols, memory
  (profile re-verified read-only against `~/Public/Agents/Original_User/profile.md`),
  sessions (index + active session's summary/notes/transcript), the plan,
  worklog, todos and scaffold READMEs as applicable.
- Append a one-line checkpoint to
  [`../work_history/auto_update.log`](../work_history/auto_update.log).

## Reporting

Silent by default; a brief `Files auto-updated at <time>` line when useful.
A full report is given only when Arnob issues the `Update-files` command.

**Last checkpoint:** 2026-11-19 23:09:35 +06:00 (Asia/Dhaka) — protocol defined
and first session checkpoint recorded.
