# Protocol: `Update-files`

**Defined:** 2026-11-19 23:01:54 +06:00 (Asia/Dhaka)
**Trigger:** Whenever Arnob issues `Update-files` as a command (case-insensitive).
**Owner:** OpenCode (`~/Public/Agents/OpenCode`)

**Session-scoped variant:** [auto_update.md](auto_update.md) — the same refresh,
triggered automatically during active sessions; no external scheduler.

## What it does

On the trigger, update **every file in this workspace** so the system reflects
the latest state, with real dates/timestamps and details of what changed. Then
give Arnob a report/affirmation. No clarification needed — just do it.

## Timestamp rule

Never invent a time. Read the system clock in Dhaka:

```
TZ=Asia/Dhaka date '+%Y-%m-%d %H:%M:%S +06:00 (Asia/Dhaka)'
```

Format: `YYYY-MM-DD HH:MM:SS +06:00 (Asia/Dhaka)`.

## Scope

Only `~/Public/Agents/OpenCode/`. Other agents' folders
(`Antigravity/`, `Original_User/`) are read-only references.

## Per-file update rules

| File | What to update |
| --- | --- |
| `README.md` | Refresh structure/pointers if files changed; `Last updated:` footer. |
| `index.md` | Refresh pointers and "Today"; `Last updated:` footer. |
| `agents/registry.md` | Confirm roster rows; note new/changed agents; footer. |
| `agents/messages/README.md` | Current message-queue status; footer. |
| `agents/tasks/README.md` | Current task-queue status; footer. |
| `protocols/agent_communication.md` | Note convention changes; footer. |
| `protocols/update_files.md` | `Last executed:` with time + summary. |
| `memory/user_profile.md` | Re-verify against `~/Public/Agents/Original_User/profile.md`; record time. |
| `memory/decisions.md` | Add decisions since last run, with date + rationale. |
| `memory/lessons.md` | Add lessons since last run. |
| `sessions/index.md` | Add/update session rows; footer. |
| `sessions/<session>/summary.md` | Append "What was done"/"Not yet done" for the active session. |
| `sessions/<session>/notes.md` | Append notes from the latest exchange. |
| `sessions/<session>/transcript.md` | Append the latest user request + OpenCode action. |
| `plans/centralized_agentic_system.md` | Update status/progress with date. |
| `work_history/worklog.md` | Add a dated entry for the day's work. |
| `todos/index.md` | Check off completed items; add new ones. |
| `contexts/README.md`, `database/README.md`, `configs/README.md`, `settings/README.md` | Note current state; footer. |

## Report / affirmation format

1. `Update-files complete — <timestamp>`.
2. List of files updated.
3. What changed (timestamps, decisions, session and worklog entries).
4. Affirmation: "All files in the OpenCode workspace are up to date."

**Last executed:** 2026-11-27 23:30:27 +06:00 (Asia/Dhaka) — full workspace
refresh; profile re-verified (7/7); both queues checked (0/0); git state
verified unchanged; report delivered to Arnob; changes committed and pushed with
`[opencode]` attribution.
**Last revised:** 2026-11-27 23:30:27 +06:00 (Asia/Dhaka) — execution record
updated; protocol rules unchanged.
