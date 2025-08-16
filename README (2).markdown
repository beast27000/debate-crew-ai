# Debate Crew AI

A Crew AI-based project that simulates a debate on a given motion, with one agent proposing, another opposing, and a judge deciding the winner based on the arguments presented.

## Table of Contents
- [Overview](#overview)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Overview
Debate Crew AI is a Python project utilizing the Crew AI framework to orchestrate a debate. It includes two agents: a debater (arguing for or against a motion) and a judge (evaluating arguments to determine the winner). The motion is configurable, with the default being: "There needs to be strict laws to regulate LLMs."

The project uses YAML configuration files to define agents and tasks, and outputs the arguments and decision to Markdown files in the `output/` directory.

## Project Structure
```
debate/
├── src/
│   ├── debate/
│   │   ├── config/
│   │   │   ├── agents.yaml       # Agent configurations (debater and judge)
│   │   │   ├── tasks.yaml        # Task configurations (propose, oppose, decide)
│   │   ├── crew.py               # Crew AI setup for agents, tasks, and crew
│   ├── main.py                   # Entry point to run the debate
├── output/
│   ├── propose.md                # Output file for the propose argument
│   ├── oppose.md                 # Output file for the oppose argument
│   ├── decide.md                 # Output file for the judge's decision
└── README.md                     # This file
```

## Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/debate-crew-ai.git
   cd debate-crew-ai
   ```

2. **Set up a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install crewai
   ```

4. **Install required LLMs**:
   - The debater uses `ollama/llama3.2`. Follow instructions at [Ollama](https://ollama.ai/) to set it up.
   - The judge uses `gemini-2.5-flash`. Ensure you have access to Google's LLM provider and configure credentials as needed.

## Usage
1. **Run the debate**:
   ```bash
   python src/main.py
   ```

2. **Input motion**:
   - The default motion is: "There needs to be strict laws to regulate LLMs."
   - Modify the `motion` in `src/main.py` to change the debate topic:
     ```python
     inputs = {
         'motion': 'Your custom motion here',
     }
     ```

3. **Outputs**:
   - Arguments and the judge's decision are saved in:
     - `output/propose.md` (argument in favor)
     - `output/oppose.md` (argument against)
     - `output/decide.md` (judge's decision)

## Configuration
- **Agents**: Defined in `src/debate/config/agents.yaml`
  - `debater`: Uses `ollama/llama3.2` to argue for or against the motion.
  - `judge`: Uses `gemini-2.5-flash` to evaluate arguments impartially.
  - To use Google Gemini for the debater, update `agents.yaml` to match the judge's configuration:
    ```yaml
    debater:
      role: >
        A compelling debater
      goal: >
        Present a clear argument either in favor of or against the motion. The motion is: {motion}
      backstory: >
        You're an experienced debater with a knack for giving concise but convincing arguments.
        The motion is: {motion}
      llm: gemini-2.5-flash
      llm_provider: google
    ```

- **Tasks**: Defined in `src/debate/config/tasks.yaml`
  - `propose`: Argument in favor of the motion.
  - `oppose`: Argument against the motion.
  - `decide`: Judge's evaluation and decision.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.