# Protocol: Update-files Trigger

## Trigger Conditions
- **Manual Trigger**: `Update-files` (case-insensitive).
- **Active-Conversation Auto-Sync**: Natural checkpoints during active interactions (roughly every ~10 minutes of active back-and-forth conversation, or upon completing major task milestones).
- **Idle State**: Strictly passive. When no conversation or active task is occurring, no background processes run and no phantom updates are executed.

## Objective
When Arnob issues the trigger, Antigravity must execute a complete state update across its workspace files with explicit timestamps, dates, and action details, then return a concise affirmation and report.

## Execution Checklist
1. **Timestamp Identification**:
   - Capture current ISO timestamp and local datetime (Dhaka, UTC+6).
2. **Session Log**:
   - Update current session file under `sessions/` or create a new session file if this is a new date/session.
   - Record user prompts, tasks accomplished, decisions made, and pending actions.
   - Update `sessions/index.md` if a new session entry was created.
3. **Task & Planning Boards**:
   - Review and update `tasks/todo.md` (check off completed items, add newly mentioned tasks).
   - Update `tasks/active_plan.md` to reflect the latest phase progress and timestamps.
4. **Memory & Context**:
   - If any new user preferences, tools, conventions, or global knowledge were introduced, record them in `memory/user_preferences.md` or `memory/global_knowledge.md`.
5. **Work History / Changelog**:
   - Append an entry in `work_history/changelog.md` detailing the exact modifications, files changed, and timestamp.
6. **Reporting**:
   - Present a clear, formatted summary to Arnob listing all updated files, changes made, and current status.
