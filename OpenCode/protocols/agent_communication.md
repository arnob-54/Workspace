# Protocol: Agent Communication

How agents in Arnob's workforce talk to each other through the common folder
`~/Public/Agents`. Plain markdown + YAML frontmatter — no code changes needed.
All paths below are relative to the common folder unless noted.
**Last updated:** 2026-11-27 23:30:27 +06:00 (Asia/Dhaka) — `Update-files` run; conventions unchanged.

## 1. Messages — `agents/messages/`

File name: `agents/messages/YYYYMMDD_HHMM_from_to_slug.md`

Frontmatter:

```yaml
from: opencode
to: antigravity                    # agent id, or "all" for broadcast, or "user"
timestamp: 2026-11-19
type: request | response | broadcast | note
related_session: sessions/2026-11-19_centralized_agentic_system
```

Rules:
- Messages are append-only. Agents process messages where `to` is their agent
  id or `all`, and move processed ones to `agents/messages/archive/` (their own
  files only).
- `request`/`response` pair for tasks; `broadcast` is for `to: all`; `note` is
  informational.

## 2. Tasks — `agents/tasks/`

File name: `agents/tasks/<id>.md` (e.g. `task-20261119-001.md`)

Frontmatter:

```yaml
id: task-20261119-001
title: Refactor the build script
assignee: antigravity
status: open | in_progress | done
created: 2026-11-19
updated: 2026-11-19
result: (summary + links when done)
```

Rules:
- On picking up: set `status: in_progress`, note the agent in the body.
- On `done`: write the `result` and move the file to `agents/tasks/archive/`.

## 3. Handoffs

When handing work to another agent:
1. Drop a `request` message with enough context.
2. Close or reassign the task if one exists.
3. End the source session with a summary noting the handoff.

## 4. First steps for any agent

1. Read `index.md` and `agents/registry.md` (orient: find yourself and others).
2. Scan `agents/messages/` for mail to you or `all`.
3. Scan `agents/tasks/` for open tasks assigned to you.
4. When done: note useful decisions in `memory/`, append to
   `work_history/worklog.md`, and update the session folder (`summary.md`).

## 5. Git sync

`~/Public/Agents` is a git repo. Pull before starting work that depends on
others; commit and push when done. Commit messages start with `[agent-id]` to
mark the author.

## 6. Commands from Arnob

`Update-files` — see [update_files.md](update_files.md). On that command, all
files in this workspace are refreshed with real dates/timestamps and details,
then a report is given. During active sessions, the same refresh also happens
automatically at checkpoints — see [auto_update.md](auto_update.md).
