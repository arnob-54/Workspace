# Plan: Centralized Agentic System

**Status:** skeleton implemented 2026-11-19; `Update-files` command defined
23:01:54; session-scoped auto-update defined 23:09:35 (no scheduler installed);
remote sync completed by Antigravity on 2026-11-20; latest `Update-files` run
2026-11-20 12:13:51 +06:00; skills/plugins scaffolds added 2026-11-23
20:42:26 +06:00.

## Goal

A centralized, file-based agentic system shared by Arnob's agents:

- Common folder: `~/Public/Agents` — one folder where all agents keep their
  files; synced as a git repo so the workforce can pull/push between machines
  (GitHub/GitLab).
- Per-agent workspace: each agent works in its own folder. This agent's is
  `~/Public/Agents/OpenCode`.

## Layout

```
~/Public/Agents/
├── Antigravity/                # another agent (its workspace)
├── OpenCode/                   # this agent's workspace (skeleton created 2026-11-19)
│   ├── README.md
│   ├── index.md
│   ├── agents/
│   │   ├── registry.md
│   │   ├── messages/README.md
│   │   └── tasks/README.md
│   ├── protocols/
│   │   ├── agent_communication.md
│   │   ├── update_files.md
│   │   └── auto_update.md
│   ├── memory/user_profile.md, decisions.md, lessons.md
│   ├── sessions/
│   │   ├── index.md
│   │   └── 2026-11-19_centralized_agentic_system/{summary.md,notes.md,transcript.md}
│   ├── plans/centralized_agentic_system.md
│   ├── work_history/worklog.md, work_history/auto_update.log
│   ├── todos/index.md
│   └── scaffolds: contexts/, database/, configs/, settings/, skills/, plugins/
└── Original_User/profile.md    # Arnob's user profile (canonical user data)
```

## Design

1. **Communication = files in the common folder** (no broker). Agents drop
   messages to `agents/messages/` and tasks to `agents/tasks/`; anyone reads
   what is addressed to them or to `all`.
2. **Registry** — `agents/registry.md`: agent id, name, workspace folder,
   purpose. Each agent lists itself; humans can add rows too.
3. **Messages** — `agents/messages/YYYYMMDD_HHMM_from_to_slug.md` with
   frontmatter `from`, `to` (agent id | `all` | `user`), `timestamp`, `type`
   (`request`, `response`, `broadcast`, `note`). Processed messages move to
   `agents/messages/archive/` (each agent archives its own).
4. **Tasks** — `agents/tasks/<id>.md` with frontmatter `id`, `title`,
   `assignee`, `status` (`open`, `in_progress`, `done`), `created`, `updated`,
   `result`. On `done`, move the task to `agents/tasks/archive/` with the
   result.
5. **Handoffs** — drop a message + end the source session with a summary.
6. **Memory** — `memory/`: `user_profile.md` (user data; canonical source
   `~/Public/Agents/Original_User/profile.md`), `decisions.md` (key decisions
   + rationale), `lessons.md` (cross-session lessons).
7. **Sessions** — `sessions/YYYY-MM-DD_slug/` per agent–user session with
   `summary.md` (what happened), `notes.md`, `transcript.md` (key dialogue).
   `sessions/index.md` lists them.
8. **Work history** — `work_history/worklog.md`: daily entries per agent.
9. **Todos** — `todos/index.md` + `todo-<slug>.md` per item.
10. **Protocols** — `protocols/agent_communication.md` defines the
    conventions in 3–5 plus usage rules for agents.
11. **Database** — `database/`: structured data (`tasks.json`, `jobs.json`),
    created when needed.
12. **Sync** — `~/Public/Agents` is a git repo on branch `main`, remote
    `https://github.com/arnob-54/Workspace.git` (added and pushed by
    Antigravity 2026-11-20). Pull before starting work that depends on
    others; commit + push when done. Commit messages start with `[agent-id]`
    to mark the author.
13. **Command `Update-files`** — defined 2026-11-19 23:01:54 +06:00. On the
    trigger, refresh every workspace file with real dates/timestamps and
    details, then report/affirm. See
    [protocols/update_files.md](../protocols/update_files.md).
14. **Session auto-update** — defined 2026-11-19 23:09:35 +06:00. During active
    OpenCode↔Arnob sessions, the workspace is refreshed at natural checkpoints
    (same file set/timestamps as `Update-files`); no external scheduler is
    installed. Checkpoints are logged in
    `work_history/auto_update.log`. See
    [protocols/auto_update.md](../protocols/auto_update.md).
15. **Skills & plugins** — added 2026-11-23 20:42:26 +06:00: `skills/` and
    `plugins/` READMEs document OpenCode V2 skill discovery (including
    `.claude/skills` compatibility) and plugin installation via
    `opencode plugin add`. Official docs: `opencode.ai/docs/skills` and
    `opencode.ai/docs/plugins`.

**Last updated:** 2026-11-23 20:42:26 +06:00 (Asia/Dhaka) — skills/plugins
scaffolds added.
