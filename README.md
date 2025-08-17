# Debate Crew 

## Overview

Debate Crew is a multi-agent AI system powered by [CrewAI](https://crewai.com/). This project demonstrates how agents can collaborate on research and debates, leveraging structured workflows, YAML-based configurations, and extensible tools. By default, the crew generates a `report.md` summarizing research on LLMs, but it can be extended to handle a wide range of tasks.

## Features

- **Multi-Agent Debate System**: Agents with unique roles collaborate to solve complex objectives.
- **Configurable Agents & Tasks**: Define roles/goals in `config/agents.yaml` and `config/tasks.yaml`.
- **Customizable Logic**: Extend with your own tools and arguments in `crew.py` and `main.py`.
- **Automated Reports**: Generates a `report.md` file summarizing outputs.
- **Agentic AI Workflow**: Demonstrates orchestration of multiple reasoning agents for structured debates.

## Setup Instructions

1. **Python Environment**

   Ensure Python >=3.10 <3.13 is installed. This project uses [UV](https://github.com/astral-sh/uv) for dependency management.

2. **Install UV**

   ```bash
   pip install uv
   ```

3. **Install Dependencies**

   From the root folder:

   ```bash
   crewai install
   ```

4. **Configure Environment**

   Create a `.env` file in the root folder:

   ```plaintext
   OPENAI_API_KEY=your_api_key_here
   ```

## Usage

### Step 1: Define Agents & Tasks

- Edit `src/debate/config/agents.yaml` → define your agents.
- Edit `src/debate/config/tasks.yaml` → define your tasks.

### Step 2: Run the Debate Crew

```bash
crewai run
```

This will assemble the crew, assign tasks, and create:

- `report.md`

### Step 3: Extend Functionality

- Modify `src/debate/crew.py` → add tools, logic, args.
- Modify `src/debate/main.py` → customize task inputs.

## Project Structure

```
├── src/
│   └── debate/
│       ├── config/
│       │   ├── agents.yaml    # Agent roles & goals
│       │   └── tasks.yaml     # Task definitions
│       ├── crew.py            # Core crew logic
│       └── main.py            # Entrypoint for running the crew
├── report.md                  # Auto-generated debate output
├── .env                       # Environment variables
├── pyproject.toml             # Project configuration
└── README.md                  # Documentation
```

## Notes

- Requires an `OPENAI_API_KEY` in `.env`.
- Built as a CrewAI template to explore collaborative AI agents.
- Can be extended with additional tools, data sources, and workflows.

## Future Work

- Add more specialized agents for domain-specific debates.
- Integrate external APIs for fact-checking and data gathering.
- Enable real-time debate visualization via a web UI.

## Author

**Vishevvesh**

Project developed as part of exploring CrewAI and multi-agent reasoning systems.

## Tech Stack

- **Python** 3.10+
- **CrewAI** – Multi-agent framework
- **UV** – Dependency & package management
- **YAML** – Configurable agents & tasks
- **OpenAI API** – Agent reasoning
