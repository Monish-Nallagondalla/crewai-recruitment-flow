# CrewAI Lead Score Flow

Welcome to the **CrewAI Lead Score Flow** project, powered by [crewAI](https://crewai.com). This example demonstrates how you can leverage Flows from crewAI to automate the process of scoring leads, including data collection, analysis, and scoring. By utilizing Flows, the process becomes much simpler and more efficient.

## 📋 Overview

This flow will guide you through the process of setting up an automated lead scoring system. Here's a brief overview of what will happen in this flow:

1. **Load Leads**: The flow starts by loading lead data from a CSV file named `leads.csv`.

2. **Score Leads**: The `LeadScoreCrew` is kicked off to score the loaded leads based on predefined criteria.

3. **Human in the Loop**: The top 3 candidates are presented for human review, allowing for additional feedback or proceeding with writing emails.

4. **Write and Save Emails**: Emails are generated and saved for all leads.

By following this flow, you can efficiently automate the process of scoring leads, leveraging the power of multiple AI agents to handle different aspects of the lead scoring workflow.

## ✨ Features

- **Automated Lead Scoring**: Uses AI agents to evaluate candidates based on job descriptions
- **Human-in-the-Loop**: Allows human review of top candidates for additional feedback
- **Email Generation**: Automatically generates personalized follow-up emails
- **Flow Visualization**: Interactive flow diagram to visualize the process
- **Modular Crews**: Separate crews for scoring and email response handling
- **Configurable Agents**: YAML-based configuration for agents and tasks

## 🏗️ Project Structure

```
crewai-lead-score-flow/
├── src/
│   └── lead_score_flow/
│       ├── main.py                 # Main flow orchestration
│       ├── constants.py            # Job description and skills
│       ├── types.py                # Data models
│       ├── leads.csv               # Sample lead data
│       ├── crews/
│       │   ├── lead_score_crew/    # Crew for scoring leads
│       │   │   ├── lead_score_crew.py
│       │   │   └── config/
│       │   │       ├── agents.yaml
│       │   │       └── tasks.yaml
│       │   └── lead_response_crew/ # Crew for email responses
│       │       ├── lead_response_crew.py
│       │       └── config/
│       │           ├── agents.yaml
│       │           └── tasks.yaml
│       └── utils/
│           └── candidateUtils.py   # Helper functions
├── crewai_flow.html               # Flow visualization
├── pyproject.toml                 # Project configuration
├── uv.lock                        # Dependency lock file
└── README.md
```

## 🤖 AI Agents

### Lead Score Crew
- **HR Evaluation Agent**: Analyzes candidates' qualifications and compares them against the job description to provide a score and reasoning.

### Lead Response Crew
- **Email Followup Agent**: Composes personalized follow-up emails to candidates based on their bio and whether they are being pursued for the job.

## 📦 Installation

Ensure you have Python >=3.10 <=3.13 installed on your system. First, if you haven't already, install CrewAI:

```bash
pip install crewai
```

Next, navigate to your project directory and install the dependencies:

1. First lock the dependencies and then install them:

```bash
crewai install
```

### Customizing & Dependencies

**Add your `OPENAI_API_KEY` into the `.env` file**  
**Add your `SERPER_API_KEY` into the `.env` file**

## 🚀 Running the Project

### Run the Flow

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
crewai run
```

or

```bash
uv run kickoff
```

### Plot the Flow

```bash
uv run plot
```

This command initializes the lead_score_flow, assembling the agents and assigning them tasks as defined in your configuration.

When you kickstart the flow, it will orchestrate multiple crews to perform the tasks. The flow will first collect lead data, then analyze the data, score the leads and generate email drafts.

## 📊 Flow Visualization

Open `crewai_flow.html` in your browser to see an interactive visualization of the lead scoring flow.

## ⚙️ Configuration

The project uses YAML configuration files for agents and tasks:

- `src/lead_score_flow/crews/lead_score_crew/config/agents.yaml`
- `src/lead_score_flow/crews/lead_score_crew/config/tasks.yaml`
- `src/lead_score_flow/crews/lead_response_crew/config/agents.yaml`
- `src/lead_score_flow/crews/lead_response_crew/config/tasks.yaml`

You can modify these files to customize the behavior of the AI agents.

## 📝 Dependencies

- crewai[tools]==0.85.0
- langchain-tools>=0.1.34
- crewai-tools>=0.12.0
- google-auth-oauthlib>=1.2.1
- google-api-python-client>=2.145.0
- pyvis>=0.3.2
- asyncio>=3.4.3

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

If you have any questions or issues, please open an issue on GitHub.


