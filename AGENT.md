# AGENT CORE DIRECTIVE (v1.0)

## 1. Operating Principles
- **Reliability First:** Use deterministic scripts (Python) over LLM "guessing."
- **Atomic Operations:** Break big tasks into small, testable scripts in `/execution/`.
- **Statelessness:** Local files are disposable. Final data lives in Cloud services.

## 2. Directory Structure (The Scaffolding)
Every project folder must contain:
- `/.tmp/` -> Temporary processing files.
- `/execution/` -> Final, verified scripts.
- `/directives/` -> Specific SOPs for the project.
- `AGENT.md` -> A copy of these rules.
