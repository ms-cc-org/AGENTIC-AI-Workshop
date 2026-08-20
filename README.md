# Chatbot, Workflow, or Agent?

## Choosing the Right AI Architecture for Research

> **Build AI systems. More importantly, learn when *not* to.**

Artificial intelligence is transforming research, teaching, and administration. Alongside large language models has come a new generation of AI systems capable of planning, using tools, retrieving information, and completing multi-step tasks.

These systems are commonly called **AI agents**.

But what actually makes something an agent? When is an agent appropriate? And when is a chatbot or a simple workflow the better solution?

This workshop answers those questions through a series of hands-on Google Colab notebooks designed specifically for researchers, faculty, research support professionals, higher education staff, and graduate students.

Rather than teaching a specific framework, participants learn the **fundamental architecture** behind modern AI systems by building progressively more capable examples using transparent Python code.

The goal is not simply to teach participants how to build an agent. It is to help them make better decisions about **which AI architecture is appropriate for a given problem.**

---

# Learning Objectives

By the end of this workshop, participants will be able to:

- Explain the differences between chatbots, deterministic workflows, and AI agents.
- Describe how AI agents use planning, tools, memory, and state.
- Build simple tool-using AI systems in Google Colab.
- Explain how AI agents make decisions during task execution.
- Identify situations where an AI agent is appropriate—and where a simpler solution is preferable.
- Recognize common limitations, risks, and the importance of human oversight.
- Apply these concepts to research, teaching, and administrative workflows.

---

# Intended Audience

This workshop is designed for:

- Faculty
- Researchers
- Research software engineers
- Research computing professionals
- Graduate students
- Higher education staff and administrators

No prior experience with AI agents is required.

Basic Python familiarity is helpful but not required.

---

# Workshop Philosophy

Many AI workshops teach participants how to use a particular framework or AI product.

This workshop instead teaches **how to think about AI system design.**

Participants learn the core concepts that remain useful regardless of which AI tools become popular in the future.

Throughout the workshop, participants repeatedly answer one central question:

> **Should this problem be solved with a chatbot, a workflow, or an AI agent?**

Learning to answer that question is more valuable than learning any single framework or SDK.

To keep the workshop focused on concepts rather than provider-specific implementation details, the notebooks use **Anthropic as the reference LLM provider**. The architectural concepts transfer directly to other providers and future AI frameworks.

---

# Workshop Roadmap

The workshop consists of four notebooks that progressively build a simple research assistant.

---

## Notebook 1 — Chatbot vs. Workflow vs. Agent

Compare three different approaches to solving the same problem:

- A chatbot
- A deterministic workflow
- A tool-using AI agent

Participants observe how each architecture behaves differently and learn when each approach is appropriate.

**Key concepts**

- Prompting
- Deterministic workflows
- Planning
- Tool selection
- Decision making

**Participant outcome**

Explain why chatbots, workflows, and agents behave differently and identify when each should be used.

---

## Notebook 2 — Giving an Agent Tools

Extend the AI agent by connecting it to external tools.

Participants learn how an agent:

- Chooses an appropriate tool
- Supplies arguments
- Receives structured results
- Decides what to do next

Tools demonstrated include:

- Web search
- Document retrieval
- Structured outputs

**Participant outcome**

Understand how tool use extends an agent's capabilities and recognize the risks associated with giving AI systems access to external resources.

---

## Notebook 3 — Building a Research Assistant

Combine planning, retrieval, and synthesis into a complete research workflow.

Participants build a research assistant that can:

1. Accept a research question
2. Create a task plan
3. Retrieve supporting information
4. Organize findings
5. Produce a summarized report with citations

Rather than treating the AI model as a black box, participants inspect each step of the workflow.

**Participant outcome**

Build and understand an end-to-end AI-assisted research workflow.

---

## Notebook 4 — Memory and Multi-Step Reasoning

Extend the research assistant with:

- Short-term memory
- Task state
- Multi-step execution
- Human-review checkpoints
- Stopping conditions

Participants learn how AI systems maintain context across multiple steps and why memory differs from model training.

**Participant outcome**

Explain how memory enables more sophisticated AI workflows while recognizing when human oversight should remain part of the process.

---

# Capstone Exercise

Participants design an AI solution for a research or administrative problem.

Instead of immediately building an AI agent, they first determine the most appropriate architecture.

For each scenario, participants evaluate:

| Question | Description |
|-----------|-------------|
| Architecture | Chatbot, workflow, or agent? One sentence justification. |
| Goal | What problem should be solved? |
| Users | Who interacts with the system? |
| Inputs | What information is available? |
| Outputs | What should the system produce? |
| Tools | What external capabilities are required? |
| Memory | What information must persist? |
| Risks | What could fail or produce incorrect results? |
| Human Review | Where should a person remain in the loop? |

Participants should be able to justify why the problem is best solved with:

- A chatbot
- A deterministic workflow
- An AI agent

---

# Running the Workshop

The notebooks are designed to run in **Google Colab**.

No local installation is required.

---

## Mock Mode (Recommended)

Every notebook supports a fully scripted demonstration mode.

```python
PROVIDER = "mock"
```

Mock mode:

- Requires no API key
- Makes no external model calls
- Produces deterministic outputs
- Allows participants to inspect every step of the workflow
- Supports classroom instruction without paid AI accounts

Mock mode demonstrates **system behavior**, not model quality.

---

## Live Model (Optional)

Participants who wish to experiment with a live model may optionally use **Anthropic**.

```python
PROVIDER = "anthropic"
```

An Anthropic API key is required.

API usage may incur charges.

The workshop is fully functional in mock mode and does **not** require a paid account.

---

## Google Colab Setup

1. Open the notebook in Google Colab.
2. Open the **Secrets** panel.
3. Add your Anthropic API key (optional).
4. Grant notebook access to the secret.
5. Select the desired provider.
6. Restart the runtime.
7. Run the notebook from the beginning.

Never place API keys directly into notebook cells, screenshots, or committed files.

---

# Responsible AI

This workshop uses only:

- Public information
- Synthetic data
- De-identified examples
- Institutionally approved datasets

Participants should **not** upload:

- Unpublished research
- Human-subject or patient data
- Personally identifiable information
- Student educational records
- Confidential institutional information
- Grant-sensitive material
- API keys or credentials

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
├── LICENSE
├── Images/
├── notebooks/
│   ├── 01_chatbot_vs_agent.ipynb
│   ├── 02_tool_using_agent.ipynb
│   ├── 03_research_assistant.ipynb
│   └── 04_memory_multistep.ipynb
├── datasets/
└── docs/
```

- `notebooks/` — Participant notebooks
- `datasets/` — Public, synthetic, or de-identified sample data
- `docs/` — Project documentation and validation protocols
- `Images/` — Diagrams and workshop illustrations
- `requirements.txt` — Dependencies for optional local execution

## Responsible use and data boundaries

Use only public, synthetic, de-identified, or institutionally approved information during this workshop.

Do not send the following information to an AI provider unless your institution has explicitly approved the provider, account, configuration, and intended use:

- Unpublished research
- Human-subject or patient data
- Personally identifiable information
- Student educational records
- Confidential institutional information
- Grant-sensitive material
- API keys or credentials

Removing names from a document does not necessarily make it safe to upload.

When in doubt, consult your institution's privacy, security, legal, or research compliance office.

---

# Important Limitations

These notebooks are educational demonstrations—not production systems.

Participants should always:

- Verify important claims.
- Review retrieved evidence.
- Inspect tool inputs and outputs.
- Keep humans involved in consequential decisions.
- Use deterministic software when the workflow is already known.
- Avoid granting AI systems unnecessary permissions.

---

# Validation Standard

A notebook is considered ready for learner delivery only when:

- It runs from beginning to end in a clean Google Colab environment.
- Mock mode functions without API credentials.
- Anthropic support has been validated or explicitly marked as unverified.
- Code, markdown, examples, and outputs are internally consistent.
- Documentation matches the implementation.
- Repository links, notebook names, and file references are correct.
- A reviewer other than the author has completed the notebook from a learner's perspective.
- Validation findings have been corrected and retested.

Technical defects and documentation issues should be tracked through GitHub Issues.

---

# Contributing

Contributions are welcome.

When submitting changes:

- Keep examples appropriate for beginners.
- Avoid unnecessary framework-specific complexity.
- Test notebooks from a clean Colab runtime.
- Include validation evidence.
- Update documentation alongside code.
- Submit changes for review before considering them complete.

Never commit:

- API keys
- Confidential information
- Restricted datasets
- Sensitive research material

---

# License

- Source code and executable notebook cells are licensed under the [MIT License](https://opensource.org/license/mit). See `LICENSE` for the complete terms.
- Workshop explanations, exercises, diagrams, and other non-code materials are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

Third-party libraries, datasets, trademarks, logos, model outputs, and externally sourced materials remain subject to their respective licenses and terms.
