# Debate Crew – Vishevvesh

## Overview

Debate Crew is a multi-agent AI system powered by [CrewAI](https://crewai.com/). This project demonstrates how agents can collaborate on research and debates, leveraging structured workflows, YAML-based configurations, and extensible tools. By default, the crew generates a `report.md` summarizing research on LLMs, but it can be extended to handle a wide range of tasks.
ed configurations, and extensible tools. By default, the crew generates a `report.md` summarizing research on LLMs, but it can be extended to handle a wide range of tasks.

## Features

- **Multi-Agent Debate System**: Agents with unique roles collaborate to solve complex objectives.
- **Configurable Agents & Tasks**: Define roles/goals in `config/agents.yaml` and `config/tasks.yaml`.
- **Customizable Logic**: Extend with your own tools and arguments in `crew.py` and `main.py`.
- **Automated Reports**: Generates a `report.md` file summarizing outputs.
- **Agentic AI Workflow**: Demonstrates orchestration of multiple reasoning agents for structured debates.

## Understanding Your Crew

The Debate Crew is composed of multiple AI agents, each with unique roles, goals, and tools.

- Tasks are defined in `src/debate/config/tasks.yaml`, describing what the crew must achieve.
- Agent configurations are stored in `src/debate/config/agents.yaml`, outlining their capabilities and collaboration style.
- During execution, the crew coordinates these agents to leverage their collective skills and achieve complex objectives.
- This modular setup allows you to easily expand, specialize, or reconfigure your team of agents to tackle new domains.
  

![WhatsApp Image 2025-07-05 at 21 45 44_5e07d3a3](https://github.com/user-attachments/assets/a2ac550a-6cf5-4fcb-be48-cd8d2c789a80)
![WhatsApp Image 2025-07-05 at 21 46 06_0915d376](https://github.com/user-attachments/assets/d646dc0e-9577-493a-ac9b-3664318555ec)
![WhatsApp Image 2025-07-05 at 21 46 23_818e724f](https://github.com/user-attachments/assets/00bfe3b0-1cbb-45bc-b14b-68a3cc54b1bb)
![WhatsApp Image 2025-07-05 at 21 48 31_23cd2e55](https://github.com/user-attachments/assets/426a3a64-aaf4-449f-9ae5-1a7e8d972630)
![WhatsApp Image 2025-07-05 at 21 49 06_ab149678](https://github.com/user-attachments/assets/3aa07415-2c26-469e-9c8f-5c4344da08f7)
![WhatsApp Image 2025-07-05 at 21 49 49_c0c50332](https://github.com/user-attachments/assets/d4492b50-7ce4-4755-b19d-63e5203974bb)
![WhatsApp Image 2025-07-05 at 21 50 07_086efda4](https://github.com/user-attachments/assets/f7bfc50d-314e-440d-9edc-afadde8baedc)
![WhatsApp Image 2025-07-05 at 21 58 00_64e69428](https://github.com/user-attachments/assets/62645a40-2452-477a-a22e-e25f26c500d7)
![WhatsApp Image 2025-07-05 at 21 58 37_8f72928d](https://github.com/user-attachments/assets/ac62bd53-4a2a-4e08-bc85-6dd5145df4ba)


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
