# Week 4 Behavioral Models

This folder contains three views of the same `generate_plan()` behavior.

- `activity-diagram.md` — actions, decisions, success and failure paths
- `state-machine-diagram.md` — the states of `StudyPlanningAgent`
- `sequence-diagram.md` — messages between Student, UI, Agent, CalendarTool, and Memory

The diagrams intentionally correspond to the executable `app.py` Week 4 application.

## Diagram-to-code traceability

| Model element | Python code |
|---|---|
| Observe assignments | `move_to(OBSERVING)` and `if not assignments` |
| WaitingForInput | `AgentState.WAITING_FOR_INPUT` |
| Call CalendarTool | `calendar_tool.get_availability()` |
| Tool failure | `except CalendarToolError` |
| Planning | `sorted(...)` and `PlanItem` creation |
| Completed | `AgentState.COMPLETED` |
| Persistent memory | `JsonMemory.append()` |
| Agent to tool sequence message | `self.calendar_tool.get_availability()` |
