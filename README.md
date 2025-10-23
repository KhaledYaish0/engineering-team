# Engineering Team

Agentic **engineering collaboration system** using multiple AI agents that plan, code, review, and document technical projects in coordination.

- Built with **CrewAI** for team‑based multi‑agent orchestration.

## Project Structure
```
engineering_team_clean/
├─ example_output_4o/
│  ├─ accounts.py
│  ├─ accounts.py_design.md
│  ├─ app.py
│  └─ test_accounts.py
├─ example_output_mini/
│  ├─ accounts.py
│  └─ app.py
├─ example_output_new/
│  ├─ accounts.py
│  ├─ accounts.py_design.md
│  ├─ app.py
│  └─ test_accounts.py
├─ knowledge/
│  └─ user_preference.txt
├─ output/
│  └─ .gitkeep
├─ src/
│  └─ engineering_team/
│     ├─ config/
│     │  ├─ agents.yaml
│     │  └─ tasks.yaml
│     ├─ tools/
│     │  ├─ __init__.py
│     │  └─ custom_tool.py
│     ├─ __init__.py
│     ├─ crew.py
│     └─ main.py
├─ .env
├─ .gitignore
├─ pyproject.toml
├─ README.md
└─ uv.lock
```
## Quick Start
### 1) Prerequisites
- Python **>= 3.10, < 3.13**
- `.env` file containing API keys:
```
OPENAI_API_KEY=sk-...
```

### 2) Install
```bash
pip install uv
uv pip install -e .
```

### 3) Configure
- Customize agents, roles, and tasks in `config/`.
- Results and reports are saved under `output/`.

### 4) Run
```bash
python -m src.engineering_team.main
```
