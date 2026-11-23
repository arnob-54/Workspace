# Workspace: Centralized Multi-Agent Workforce

[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)]()
[![Repository](https://img.shields.io/badge/GitHub-arnob--54%2FWorkspace-blue.svg)](https://github.com/arnob-54/Workspace)

Welcome to the centralized agent ecosystem repository for **Arnob** ([@arnob-54](https://github.com/arnob-54)).

This repository serves as the unified coordination hub, persistent memory store, and cross-machine synchronization platform for autonomous agentic systems (`Antigravity`, `OpenCode`, and future agents).

---

## 🏛️ Architecture & Directory Layout

```text
/home/arnob/Public/Agents/
├── README.md                  # Ecosystem entry point and documentation
├── .gitignore                 # Root protection preventing accidental secret/credential commits
│
├── Original_User/             # Single source of truth for user profile & identity
│   └── profile.md             # Canonical user details (Name, Contacts, GitHub, Preferences)
│
├── Antigravity/               # Dedicated workspace for Antigravity (Google DeepMind)
│   ├── index.md               # Master index of Antigravity subsystems
│   ├── README.md              # Antigravity operational guide
│   ├── configs/               # Settings (settings.json) and persona (persona.md)
│   ├── protocols/             # SOPs (inter_agent.md, update_files.md)
│   ├── memory/                # Persistent memory & user preferences
│   ├── sessions/              # Chronological session transcripts & session index
│   ├── tasks/                 # Active roadmap (active_plan.md) and task backlog (todo.md)
│   ├── work_history/          # Detailed changelog and execution history
│   ├── skills/                # Modular procedural skills and custom runbooks
│   ├── plugins/               # Plugin bundles & Claude Code compatible extensions
│   ├── database/              # Persistent key-value stores & local database files
│   └── contexts/              # Architecture diagrams, system models & topologies
│
└── OpenCode/                  # Dedicated workspace for OpenCode agent
    ├── index.md               # Master index of OpenCode subsystems
    ├── README.md              # OpenCode workspace overview
    ├── agents/                # Agent registry, task queues, and message bus
    ├── configs/               # Agent configurations and environment definitions
    ├── contexts/              # OpenCode contextual references
    ├── database/              # OpenCode local state databases
    ├── memory/                # Lessons, decisions, and profile references
    ├── plans/                 # Architectural plans and execution runbooks
    ├── protocols/             # Communication, file updates, and auto-update rules
    ├── sessions/              # Session logs, summaries, and transcripts
    ├── settings/              # OpenCode runtime settings
    ├── skills/                # Reusable skills/runbooks (OpenCode V2 discovery notes)
    ├── plugins/               # Plugin records and install/configuration notes
    ├── todos/                 # OpenCode task lists and progress trackers
    └── work_history/          # Worklogs and auto-update checkpoints
```

---

## ⚙️ Core Operational Protocols

### 1. Unified User Identity
All agents must reference [Original_User/profile.md](Original_User/profile.md) for user details. Agents never maintain conflicting identity definitions.

### 2. Workspace Scoping & Isolation
- Each agent system has full ownership and write permissions inside its dedicated directory (`Antigravity/`, `OpenCode/`).
- Cross-agent directories are treated as read-only unless specifically directed to write to shared coordination files.

### 3. File Synchronization Trigger (`update-files`)
Whenever instructed with `update-files` (case-insensitive), the active agent
refreshes its own workspace with real dates, local time (`Asia/Dhaka`, UTC+6)
and details, then stages, commits and pushes to GitHub with `[<agent-id>]`
attribution. Each agent keeps its own record layout, so the concrete files
differ:

| Agent | Sessions / summary | Plan & tasks | History |
| --- | --- | --- | --- |
| `Antigravity/` | `sessions/` | `tasks/active_plan.md`, `tasks/todo.md` | `work_history/changelog.md` |
| `OpenCode/` | `sessions/index.md`, `sessions/<session>/{summary,notes,transcript}.md` | `plans/centralized_agentic_system.md`, `todos/index.md` | `work_history/worklog.md`, `work_history/auto_update.log` |

Common to both: re-verify [Original_User/profile.md](Original_User/profile.md),
stamp the time from the system clock (never estimate it), refresh the per-agent
README/index, and deliver a report/affirmation to Arnob.

### 4. Zero-Background Idle State
Background daemons and polling loops remain dormant when not actively conversing with the user. State synchronization occurs at natural checkpoints during active sessions or via explicit manual triggers. OpenCode's session-scoped rule is defined in [`OpenCode/protocols/auto_update.md`](OpenCode/protocols/auto_update.md); no cron job, systemd timer or daemon is installed.

### 5. Secret & Credential Protection
The root [.gitignore](.gitignore) strictly excludes `.env`, `*.key`, `*.token`, `scratch/`, and temporary build artifacts to ensure no credentials or sensitive tokens are ever committed to version control.

---

## 🚀 Quick Start / Multi-Machine Restoration

To restore this workspace on another machine:

```bash
# Navigate to the target directory
cd /home/arnob/Public

# Clone specifying the 'Agents' folder to match canonical path structure
git clone https://github.com/arnob-54/Workspace.git Agents

# Enter the workspace
cd Agents
```

> [!NOTE]
> Linux file paths are case-sensitive. Always clone into `/home/arnob/Public/Agents` to maintain full compatibility across internal references and relative links.

---

**Last updated:** 2026-11-23 22:36:15 +06:00 (Asia/Dhaka) — OpenCode added the
missing `skills/` and `plugins/` entries to the OpenCode tree, documented the
agent-specific `update-files` file sets, and linked the session-scoped
auto-update protocol. Contribution: `[opencode]`.
