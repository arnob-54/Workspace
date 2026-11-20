# Session Notes — 2026-11-19 (OpenCode)

- Arnob: legal name Md. Aminul Islam Ornob, public name Arnob Miah, nickname
  Arnob, GitHub arnob-54, email aminul.ornab.official@gmail.com, birthday
  2 September 2000, Dhaka, Bangladesh. Cross-checked against
  `~/Public/Agents/Original_User/profile.md`: all fields match (re-verified
  23:01:54 +06:00).
- Discussed: a common folder `~/Public/Agents` for all agents; a
  no-broker file communication system (messages + tasks); per-agent
  workspaces; git sync for the whole folder.
- Design decided: message files with frontmatter (`from`, `to`, `timestamp`,
  `type`), task files in `agents/tasks/` with status fields, agent registry,
  memory, sessions, worklog, todos, protocols, database/configs/settings
  scaffolds.
- 23:01:54 +06:00 — New command `Update-files` defined by Arnob. It means:
  update every file in this workspace (timestamp/date/details) and return a
  report/affirmation. Definition lives in `protocols/update_files.md`.
- 23:09:35 +06:00 — Auto-update is session-scoped: it happens while Arnob and
  OpenCode are actively working, not on a timer. Check `crontab`/systemd was
  investigated but nothing was installed. Definition lives in
  `protocols/auto_update.md`; first checkpoint in
  `work_history/auto_update.log`.
- 2026-11-20 10:26:13 +06:00 — OpenCode fixed the two audit findings at
  Arnob's request and made sure its contribution was recorded (worklog,
  changelog, `[opencode]` commit) and synced to GitHub.
