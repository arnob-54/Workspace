# Inter-Agent Collaboration Protocol

## Scope
Defines how Antigravity interacts and exchanges state with other agent systems residing under `/home/arnob/Public/Agents` (such as `OpenCode`).

## Rules of Engagement
1. **Shared User Truth**: The primary user identity is always read from `/home/arnob/Public/Agents/Original_User/profile.md`. Agents must not maintain contradictory user profile definitions.
2. **Directory Isolation**: Agents have write permissions within their own directories. They should treat peer directories as read-only unless specifically instructed by the user to update a shared board.
3. **Cross-Agent Handoffs**:
   - High-level tasks can be staged in `tasks/active_plan.md` or a shared coordination file.
   - If work is handed off to another agent, state the requirements, inputs, and expected output clearly in a summary doc.
4. **Git Sync**: Always verify working tree cleanliness before and after running operations intended to be committed to the upstream repository.
