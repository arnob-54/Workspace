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
    ├── todos/                 # OpenCode task lists and progress trackers
    └── work_history/          # Worklogs and audit history
```

---

## ⚙️ Core Operational Protocols

### 1. Unified User Identity
All agents must reference [Original_User/profile.md](Original_User/profile.md) for user details. Agents never maintain conflicting identity definitions.

### 2. Workspace Scoping & Isolation
- Each agent system has full ownership and write permissions inside its dedicated directory (`Antigravity/`, `OpenCode/`).
- Cross-agent directories are treated as read-only unless specifically directed to write to shared coordination files.

### 3. File Synchronization Trigger (`update-files`)
Whenever instructed with `update-files`, the active agent:
1. Stamps the current date and local time (`Asia/Dhaka`, UTC+6).
2. Appends conversation and task summaries to `sessions/`.
3. Updates `tasks/active_plan.md` and `tasks/todo.md`.
4. Records changes into `work_history/changelog.md`.
5. Stages, commits, and pushes clean state updates to GitHub.

### 4. Zero-Background Idle State
Background daemons and polling loops remain dormant when not actively conversing with the user. State synchronization occurs at natural checkpoints during active sessions or via explicit manual triggers.

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
