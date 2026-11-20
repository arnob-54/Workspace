# Workspace: Centralized Multi-Agent Workforce

Welcome to the centralized agent ecosystem repository for **Arnob** ([@arnob-54](https://github.com/arnob-54)).

This repository serves as the shared state, memory, configuration, and coordination space for autonomous agentic systems running across multiple workstations.

---

## Architecture Overview

```text
/home/arnob/Public/Agents/
├── Original_User/         # Single source of truth for user profile & identity
│   └── profile.md
├── Antigravity/           # Dedicated workspace for Antigravity agent
│   ├── configs/           # Settings, preferences, and persona definition
│   ├── protocols/         # SOPs, inter-agent communication, and sync rules
│   ├── memory/            # Knowledge base and user preferences
│   ├── sessions/          # Session logs and indexed interaction history
│   ├── tasks/             # Active roadmap, todo list, and completed items
│   └── work_history/      # Execution changelog and work history
└── OpenCode/              # Dedicated workspace for OpenCode agent
    ├── configs/           # Configs and READMEs
    ├── database/          # Local databases and state
    ├── memory/            # Decisions, lessons, and profile references
    ├── plans/             # Architecture and implementation plans
    ├── protocols/         # Communication and update protocols
    ├── sessions/          # OpenCode interaction logs
    └── todos/             # OpenCode task lists
```

---

## Core Guidelines

1. **User Identity Consistency**: All agents must reference [Original_User/profile.md](Original_User/profile.md) for identity details.
2. **Directory Isolation**: Each agentic system primarily manages its own directory. Inter-agent communication follows shared protocols.
3. **Cross-Machine Synchronization**: Changes are version-controlled and synchronized via Git with [arnob-54/Workspace](https://github.com/arnob-54/Workspace).
4. **Secret Protection**: Credentials, API tokens, and private keys must never be committed; the root `.gitignore` enforces exclusion.
