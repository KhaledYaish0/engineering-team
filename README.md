# Engineering Team

A **CrewAI multi-agent system** that transforms a single set of requirements into a **complete software module** — including design, backend implementation, frontend demo, and tests.

---

## Overview

The Engineering Team automates collaboration between specialized agents:

| Agent | Role | Output |
|-------|------|---------|
| **Engineering Lead** | Designs backend architecture | `output/{module_name}_design.md` |
| **Backend Engineer** | Implements the backend module | `output/{module_name}` |
| **Frontend Engineer** | Builds a Gradio demo app | `output/app.py` |
| **Test Engineer** | Writes unit tests | `output/test_{module_name}` |

---

## Quick Start

### 1. Installation
```bash
pip install uv
uv pip install -e .
```

Or manually:
```bash
python -m venv .venv
. .venv/Scripts/activate  # Windows
# source .venv/bin/activate  # macOS/Linux
pip install -e .
```

### 2. Environment
Create a `.env` file in the root:
```
OPENAI_API_KEY=sk-...
```

### 3. Run
```bash
python -m src.engineering_team.main
```

This will sequentially generate:
1. Design (`{module_name}_design.md`)
2. Backend (`{module_name}`)
3. UI (`app.py`)
4. Tests (`test_{module_name}`)

---

## Configuration

You define the **requirements**, `module_name`, and `class_name` in the runtime input, e.g.:

```python
inputs = {
  "requirements": "- CRUD TODOs\n- Persist to todos.json\n- Search/filter by completed",
  "module_name": "todo_backend.py",
  "class_name": "TodoBackend"
}
```

---

## Folder Structure

```
engineering_team/
├─ src/engineering_team/
│  ├─ config/
│  │  ├─ agents.yaml
│  │  └─ tasks.yaml
│  ├─ main.py
│  └─ ...
├─ output/
│  ├─ {module_name}_design.md
│  ├─ {module_name}
│  ├─ app.py
│  └─ test_{module_name}
└─ .gitignore
```

---

## Agents Summary

- **Engineering Lead** → writes backend design (Markdown spec)
- **Backend Engineer** → writes executable module
- **Frontend Engineer** → writes `app.py` (Gradio demo)
- **Test Engineer** → writes unit tests

---

## Test & Demo

```bash
cd output
pytest -q test_{module_name}
python app.py
```
