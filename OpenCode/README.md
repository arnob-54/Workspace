# OpenCode — Arnob's Agent Workspace

`~/Public/Agents` is the common folder of Arnob's agentic workforce: every
agent keeps its files there, and the folder is synced as a git repo so the
system can be pulled/pushed between machines.

This folder is this agent's workspace: **OpenCode**.

## Structure

- [`index.md`](index.md) — master index
- [`agents/`](agents/) — agent roster and inter-agent communication
  ([`registry.md`](agents/registry.md), `messages/`, `tasks/`)
- [`memory/`](memory/) — user data:
  [`user_profile.md`](memory/user_profile.md),
  [`decisions.md`](memory/decisions.md),
  [`lessons.md`](memory/lessons.md)
- [`sessions/`](sessions/) — one folder per agent–user session (`YYYY-MM-DD_slug/`)
- [`plans/`](plans/) — plans:
  [`centralized_agentic_system.md`](plans/centralized_agentic_system.md)
- [`protocols/`](protocols/) — conventions:
  [`agent_communication.md`](protocols/agent_communication.md),
  [`update_files.md`](protocols/update_files.md),
  [`auto_update.md`](protocols/auto_update.md)
- `contexts/` — shared context snapshots
- `database/` — structured data (tasks, jobs, ledgers)
- `configs/` — shared configuration files
- `settings/` — settings and preferences
- [`work_history/`](work_history/) — work logs:
  [`worklog.md`](work_history/worklog.md),
  [`auto_update.log`](work_history/auto_update.log)
- [`skills/`](skills/) — reusable skills/runbooks:
  [`README.md`](skills/README.md)
- [`plugins/`](plugins/) — plugin records and configuration notes:
  [`README.md`](plugins/README.md)
- [`todos/`](todos/) — to-do lists: [`index.md`](todos/index.md)

Start by reading [`index.md`](index.md) and
[`protocols/agent_communication.md`](protocols/agent_communication.md).
When Arnob says `Update-files`, follow
[`protocols/update_files.md`](protocols/update_files.md). During active work,
follow [`protocols/auto_update.md`](protocols/auto_update.md).

**Last updated:** 2026-11-23 20:42:26 +06:00 (Asia/Dhaka) — added `skills/` and
`plugins/` scaffolds; refreshed pointers.
