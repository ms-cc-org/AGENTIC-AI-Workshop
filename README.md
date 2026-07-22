# Agentic AI for Research, Higher Education, and Administration

A hands-on introductory workshop for researchers, faculty, staff, research-support professionals, and graduate students who want to understand how AI agents work and where they may be useful.

Participants will build small agent workflows in Google Colab. The workshop focuses on fundamental concepts and transparent Python examples—not advanced agent frameworks or production deployment.

> **Project status:** This workshop is under active development. Notebooks should be considered ready for delivery only after their code, instructions, and exercises have completed end-to-end learner validation.

## Workshop goals

Most people have used an AI chatbot: provide a prompt and receive a response. An agent extends that interaction by operating within a loop, using tools, responding to results, maintaining relevant state, and continuing until it reaches a stopping condition.

By the end of the workshop, participants will be able to:

- Explain the differences among a chatbot, a predefined workflow, and an AI agent.
- Describe the principal components of an agent workflow.
- Explain how agents use tools, state, and memory.
- Build and modify a small agent workflow.
- Identify appropriate agent use cases in research, higher education, and administration.
- Recognize situations in which a chatbot or predefined workflow is preferable to an agent.
- Identify risks and appropriate points for human review.

## Intended audience

This workshop is designed for:

- Faculty and researchers
- Research-support professionals
- Higher-education staff and administrators
- Graduate students

Participants may have minimal programming experience. Basic familiarity with Python is helpful but not required.

## What participants will build

The workshop consists of four notebooks. Each notebook can run independently, while the series progressively develops the components of a small research assistant.

### Notebook 1: Chatbot, workflow, and agent

`notebooks/01_chatbot_vs_agent.ipynb`

Compare three approaches side by side:

- A chatbot that produces one response from supplied context
- A predefined workflow whose steps are selected by the developer
- A tool-using agent that can select its next action at runtime

**Participant outcome:** Explain why these systems behave differently and when each approach is appropriate.

### Notebook 2: Tool-using agent

`notebooks/02_tool_using_agent.ipynb`

Explore how an agent can interact with tools for:

- Web search
- Document retrieval
- Structured output generation

The notebook shows how a model selects a tool, supplies arguments, receives the result, and decides what to do next.

**Participant outcome:** Explain how tools extend an agent’s capabilities and identify the risks of giving an agent access to external systems.

### Notebook 3: Research assistant

`notebooks/03_research_assistant.ipynb`

Build a small research assistant that:

1. Accepts a research question.
2. Clarifies the requested outcome.
3. Creates a task plan.
4. Retrieves relevant information.
5. Organizes and synthesizes the findings.
6. Produces a summary report with source information.

**Participant outcome:** Build and inspect a complete, end-to-end agent workflow.

### Notebook 4: Memory and multi-step tasks

`notebooks/04_multistep_memory.ipynb`

Extend the assistant with:

- Task state
- Context retention
- Short-term memory
- Multi-step execution
- Stopping conditions
- Human-review checkpoints

**Participant outcome:** Explain how an agent maintains relevant context across steps and how memory differs from model training or permanent knowledge.

## Capstone exercise

Participants will design an agent for a research or administrative use case. The capstone emphasizes system design and responsible use rather than implementation complexity.

| Field               | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| Goal                | What should the agent accomplish?                             |
| Users               | Who will interact with it?                                    |
| Inputs              | What information will it receive?                             |
| Tools               | What capabilities or external systems will it need?           |
| Memory              | What context must persist across steps?                       |
| Outputs             | What should it produce?                                       |
| Risks               | What could fail, cause harm, or produce an unreliable result? |
| Human review points | Where must a person review or approve its work?               |

Participants should be prepared to explain why an agent is appropriate for the use case—or why a simpler chatbot or predefined workflow would be safer and more efficient.

## Setup

The notebooks are designed to run in **Google Colab**, so no local installation is required.

### Start without an API key

Every notebook supports a scripted demonstration mode:

```python
PROVIDER = "mock"
```

Mock mode:

- Does not call an external model.
- Does not require an API key.
- Uses predefined tool calls and responses.
- Allows participants to inspect the mechanics before using a live service.

Mock mode demonstrates program flow. It does not evaluate the quality or variability of a live model.

### Use a live model

Participants who want to use a live model may select a supported provider:

```python
PROVIDER = "openai"
```

or:

```python
PROVIDER = "anthropic"
```

A corresponding API key and an account with available usage are required. API usage may incur charges.

In Google Colab:

1. Open the **Secrets** panel using the key icon in the left sidebar.
2. Add the required provider secret.
3. Grant the notebook permission to access the secret.
4. Change `PROVIDER` in the setup cell.
5. Restart the runtime and run the notebook from the beginning.

Never paste an API key directly into a notebook cell, output, screenshot, or committed file.

Provider APIs and model names may change. Consult the provider’s current documentation if a configured model is no longer available.

## Local use

Local execution is optional. A compatible Python environment and the packages listed in `requirements.txt` are required.

```bash
git clone https://github.com/ms-cc-org/AGENTIC-AI-Workshop.git
cd AGENTIC-AI-Workshop
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Windows activation commands differ by shell. Google Colab is the recommended environment for workshop participants.

## Repository structure

```text
AGENTIC-AI-Workshop/
├── README.md
├── requirements.txt
├── LICENSE-CODE
├── LICENSE-CONTENT
├── slides/
├── notebooks/
│   ├── 01_chatbot_vs_agent.ipynb
│   ├── 02_tool_using_agent.ipynb
│   ├── 03_research_assistant.ipynb
│   └── 04_multistep_memory.ipynb
├── datasets/
├── prompts/
└── resources/
```

- `slides/` — Workshop presentation materials
- `notebooks/` — Participant notebooks
- `datasets/` — Public, synthetic, or de-identified sample data
- `prompts/` — Reusable workshop prompt examples
- `resources/` — References and supplementary materials
- `requirements.txt` — Dependencies for optional local execution

## Responsible use and data boundaries

Use only public, synthetic, de-identified, or institutionally approved information during this workshop.

Do not send the following information to an AI provider unless your institution has explicitly approved the provider, account, configuration, and intended use:

- Unpublished research
- Confidential peer-review material
- Personally identifiable information
- Student educational records or grades
- Participant, patient, health, or human-subject data
- Personnel or financial records
- Confidential institutional, grant, or partner information
- API keys, passwords, access tokens, or restricted files

Removing a person’s name may not be sufficient to de-identify a record. When uncertain, stop and consult the appropriate privacy, information-security, research-compliance, institutional-review, or legal office.

## Important limitations

The notebooks are educational demonstrations, not production systems.

Agent outputs may be incomplete, inaccurate, unsupported, or inconsistent. Tool use does not guarantee factual correctness. Participants should:

- Verify important claims against authoritative sources.
- Review citations and retrieved documents.
- Inspect tool inputs and outputs.
- Require human approval before consequential actions.
- Use deterministic code where the required steps are already known.
- Avoid granting an agent unnecessary permissions.

## Validation standard

A workshop notebook is considered ready for delivery only when:

- The exact committed version runs from beginning to end in a clean Google Colab runtime.
- Mock mode works without API credentials.
- Each documented live-provider path has been tested or clearly identified as unverified.
- Code, tool names, examples, outputs, and explanatory text are internally consistent.
- Prerequisites and setup instructions match the actual participant experience.
- A reviewer other than the author has completed the notebook from a learner’s perspective.
- Validation findings have been corrected and retested.

Technical problems and documentation defects should be reported through the repository’s [GitHub Issues](https://github.com/ms-cc-org/AGENTIC-AI-Workshop/issues).

## Contributing

Contributions and issue reports are welcome.

When proposing a change:

1. Describe the problem or learning need.
2. Keep the material appropriate for participants with minimal programming experience.
3. Avoid unnecessary frameworks or scope expansion.
4. Test the affected notebook from a clean runtime.
5. Include relevant validation evidence.
6. Submit the change for review before treating it as delivery-ready.

Do not commit API keys, restricted data, participant information, or confidential materials.

## License

This repository uses separate licenses for software and instructional content.

### Code

Unless otherwise noted, source code and executable notebook cells are licensed under the [MIT License](https://opensource.org/license/mit). See `LICENSE-CODE` for the complete terms.

### Instructional content

Unless otherwise noted, workshop explanations, exercises, diagrams, and other non-code materials are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). See `LICENSE-CONTENT` for details.

Third-party libraries, datasets, trademarks, logos, model outputs, and externally sourced materials remain subject to their respective licenses and terms.
