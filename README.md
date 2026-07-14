# Agentic AI for Reseach, HigherED, and Administration

## Purpose

Most people already have used a chatbot, some might have built agents. The gap between a chatbot and an agent is small in code and large in what it lets you do. 

You will leave this workshop with able to do two things:
- Explain the difference between a chatbot and an agent to a colleague
- Build a small agent you can rebuild on your own afterwards.

## What you'll build

Four notebooks, each notebook self-contained adding one capability until they combine into a research assistant you can use.

1. `notebooks/01_chatbot_vs_agent.ipynb` - a chatbot and an agent, side-by-side, difference shown.
2. `notebooks/02_tool_using_agent.ipynb` - web search, document retrieval and structured outputs, with the model chosing which tool to call.
3. `notebooks/03_research_assistant.ipynb` - the full pipeline with question intake, plan, retrieval, embeddings.
4. `notebooks/04_multistep_memory.ipynb` - memory, reasoning, and multi-step task execution.

## Setup

Everything runs in **Google Collab**, no installation required.

1. Open a notebook in collab.
2. You do **not** need an API key to start. Every notebook has canned replies in `"mock "` mode.
3. You can set `PROVIDER = "anthropic"` or `"openai"` in the setup cell. Make sure to add your key (in Colab, the kwy icon in the left sidebar). An Agent is pattern, not a vendor specific service.

## Repository layout

```
AGENTIC-AI-Workshop/
|-- README.md
|-- requirements.txt # for a local run (Colab installs inline)
|-- notebooks        # the four notebooks 
```