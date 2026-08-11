# Choosing the Right AI Architecture for Research, Higher Education, and Administration

> **Build AI agents. More importantly, learn when *not* to.**

Artificial intelligence is rapidly changing how research, teaching, and administration are done. Along with large language models has come a new buzzword: **AI agents**.

Researchers are hearing about agentic search, research assistants, coding agents, multi-agent systems, and autonomous workflows. But what actually makes something an *agent*? And when is an agent genuinely useful instead of unnecessarily complex?

This workshop answers those questions through a series of hands-on Google Colab notebooks designed for researchers, faculty, research support professionals, administrators, and graduate students.

Rather than teaching a particular framework or vendor, this workshop focuses on the **fundamental concepts** behind modern agentic systems. Participants progressively build increasingly capable AI systems while learning how to reason about when a chatbot, workflow, or agent is the appropriate solution.

---

# Learning Objectives

By the end of this workshop, participants will be able to:

- Explain the differences between a chatbot, a workflow, and an AI agent.
- Describe how AI agents use planning, tools, memory, and state.
- Build simple agent workflows using transparent Python examples.
- Identify situations where an AI agent provides value—and where it does not.
- Evaluate common risks, limitations, and appropriate human oversight.
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

Basic Python familiarity is helpful but not necessary.

---

# Workshop Philosophy

Most workshops teach **how to use a particular AI framework.**

This workshop teaches **how to think about AI systems.**

The concepts introduced here are intentionally framework-independent so they remain useful as AI tools continue to evolve.

Rather than asking:

> *"How do I build an agent?"*

participants learn to ask:

> **"Should this problem be solved with a chatbot, a workflow, or an AI agent?"**

That engineering judgment is often more valuable than learning any individual framework.

---

# Workshop Roadmap

The workshop consists of four notebooks that progressively build a simple research assistant.

## Notebook 1 — Chatbot vs. Workflow vs. Agent

Build three systems that solve the same problem:

- A chatbot
- A predefined workflow
- A tool-using AI agent

Participants compare how each system behaves and learn why agents make different decisions than traditional chatbots.

**Key concepts**

- Prompting
- Workflows
- Planning
- Decision making

---

## Notebook 2 — Giving an Agent Tools

Extend the agent by allowing it to interact with external tools.

The notebook demonstrates:

- Web search
- Document retrieval
- Structured tool calls
- Tool selection
- Tool execution

Participants observe how an agent decides which tool to call and how tool results influence later decisions.

---

## Notebook 3 — Building a Research Assistant

Combine planning, retrieval, and synthesis into a complete research assistant.

The assistant will:

1. Accept a research question.
2. Clarify the requested task.
3. Create a plan.
4. Retrieve relevant information.
5. Organize findings.
6. Produce a summarized report.

Participants inspect every step of the workflow rather than treating the model as a black box.

---

## Notebook 4 — Memory and Multi-Step Reasoning

Enhance the assistant with:

- Short-term memory
- Task state
- Multi-step reasoning
- Human review checkpoints
- Stopping conditions

Participants learn how agents maintain context across multiple decisions and why memory differs from model training.

---

# Capstone Exercise

Participants design an AI solution for a research or administrative task.

Rather than immediately building an agent, they first determine the most appropriate architecture.

For each scenario they evaluate:

| Question | Description |
|-----------|-------------|
| Goal | What problem is being solved? |
| Users | Who will use the system? |
| Inputs | What information is available? |
| Outputs | What should the system produce? |
| Tools | What external capabilities are required? |
| Memory | What information must persist? |
| Risks | What could fail or produce incorrect results? |
| Human Review | Where should a person remain in the loop? |

The objective is not simply to build an agent—but to justify whether an agent is the right solution.

---

# Why This Workshop Is Different

Many AI workshops focus on learning a particular framework or coding tool.

This workshop focuses on **understanding agentic systems themselves**.

Participants learn durable concepts that transfer across platforms, including:

- Planning
- Tool use
- Memory
- State management
- Human oversight
- Evaluation
- Responsible AI design

These concepts remain useful regardless of which AI framework or provider becomes popular.

---

# Running the Workshop

The notebooks are designed to run in **Google Colab**.

No local installation is required.

## Mock Mode (Recommended)

Every notebook runs in a fully scripted demonstration mode:

```python
PROVIDER = "mock"
```

Mock mode:

- Requires no API key
- Makes no external model calls
- Produces deterministic outputs
- Allows participants to inspect every step of the workflow

This makes the workshop suitable for classrooms, training sessions, and institutions without paid AI accounts.

---

## Live Providers (Optional)

Participants may optionally run the notebooks using:

```python
PROVIDER = "openai"
```

or

```python
PROVIDER = "anthropic"
```

Live execution requires the appropriate API credentials and may incur usage costs.

---

# Responsible AI

This workshop uses only public, synthetic, de-identified, or institutionally approved information.

Participants should **not** upload:

- Unpublished research
- Personally identifiable information
- Student records
- Human-subject data
- Patient information
- Confidential institutional information
- API keys or credentials
- Restricted datasets

Throughout the workshop we discuss where human oversight should remain part of the workflow and where deterministic software may be a better solution than an autonomous agent.

---

# Important Limitations

These notebooks are educational demonstrations—not production systems.

Participants should always:

- Verify important claims.
- Review retrieved evidence.
- Inspect tool outputs.
- Keep humans involved in consequential decisions.
- Avoid granting unnecessary permissions.
- Prefer deterministic software when the required workflow is already known.

---

# Validation Standard

A notebook is considered ready for delivery only when:

- It runs from beginning to end in a clean Google Colab environment.
- Mock mode functions without API credentials.
- Every documented provider path has been validated or explicitly marked as unverified.
- Documentation matches implementation.
- Internal links and examples are correct.
- A reviewer other than the author has completed the notebook from a learner's perspective.
- Validation findings have been corrected and retested.

---

# Contributing

Contributions are welcome.

When proposing changes:

- Keep the material accessible to beginners.
- Avoid unnecessary framework-specific complexity.
- Test notebooks from a clean runtime.
- Include validation evidence.
- Submit changes for review before considering them complete.

Never commit:

- API keys
- Sensitive data
- Confidential information
- Restricted research materials

---

# License

Software and instructional content are licensed separately.

- **Code** is licensed under the MIT License.
- **Instructional content** is licensed under the Creative Commons Attribution 4.0 International License.

Third-party libraries, datasets, and other external resources remain subject to their respective licenses.
