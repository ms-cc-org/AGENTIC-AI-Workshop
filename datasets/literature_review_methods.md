# Methodological Note: Standards for AI-Assisted Systematic Literature Triage (SYNTHETIC)

> **Core Directive:** To maintain scientific rigor and reproducibility, any literature review utilizing Artificial Intelligence (AI) or Large Language Model (LLM) agents for screening must treat the AI as a semi-automated pipeline step rather than an opaque decision-maker. Every automated action must be auditable, benchmarked, and logged.

---

## 1. The Standard Workflow: Defensible Triage Stages

A defensible systematic triage requires an unbroken chain of custody for every literature record. The process must follow these five sequential phases:

```
[Phase 1: Scope] ──> [Phase 2: Search] ──> [Phase 3: Screen] ──> [Phase 4: Extract] ──> [Phase 5: Report]

```

1. **Scope & Criteria Formulation:** Define the precise research question (e.g., using PICO/SPIDER frameworks) and establish rigid, a priori inclusion and exclusion criteria.
2. **Database Query Execution:** Query designated, peer-reviewed databases (e.g., PubMed, Scopus, IEEE Xplore). Every search string, Boolean operator, and filter setting must be saved verbatim.
3. **Two-Tier Screening:** Screen records against the inclusion criteria. This is typically executed in two passes: first by Title and Abstract, followed by a Full-Text review.
4. **Template-Driven Extraction:** Extract key variables (methodologies, cohorts, outcomes) into a locked metadata template to prevent cognitive drift.
5. **PRISMA-Compliant Reporting:** Document the precise flow of records through the triage pipeline, specifying exactly how many papers were excluded at each stage and the explicit reasons for their rejection.

---

## 2. The Critical Failure Mode: "Silent Filtering" by AI

The most severe risk in AI-assisted triage is **unrecorded selection bias**. When an LLM or agentic tool is used to screen papers, it may silently drop relevant literature due to context window limits, prompt misalignment, or latent biases. If the tool's exact decision path is not recorded, the entire systematic review becomes a "black box" and loses its scientific reproducibility.

> ⚠️ **The Gold Rule of AI Triage:** If an AI agent excludes a paper and you cannot audit *exactly* why, that step is scientifically invalid.

---

## 3. Mandatory Protocols for AI Integration

To mitigate the risks of silent filtering, any study incorporating AI triage must adhere to the following three compliance pillars:

### I. Comprehensive Decision Logging

The AI tool must generate a deterministic output log. For every single record processed, the system must write to a persistent database containing:

* The unique document ID (DOI/PMID).
* The exact prompt version and model parameters (e.g., temperature set to `0.0`).
* A boolean classification (`Include` / `Exclude`).
* A structured natural-language rationale justifying the decision against the inclusion criteria.

### II. Empirical Validation (Metrics)

Before running an AI agent across an entire multi-thousand paper dataset, investigators must benchmark its performance against a gold-standard, hand-labeled validation subset (typically $n \ge 100$ papers).

Calculate and report the agent's accuracy using standard information retrieval metrics:

$$Precision = \frac{\text{True Positives}}{\text{True Positives} + \text{False Positives}}$$

$$Recall = \frac{\text{True Positives}}{\text{True Positives} + \text{False Negatives}}$$

* **Note:** In systematic reviews, **Recall is the priority metric**. A false positive (screening in a bad paper) is easily corrected during manual full-text review. A false negative (silently dropping a good paper) permanently corrupts the study. Aim for a target recall of $\ge 95\%$ on the validation set.

### III. The Systematic Triage Framework

| Triage Metric | Manual Review | Naive AI Search | Audited Agentic Triage (Recommended) |
| --- | --- | --- | --- |
| **Reproducibility** | High (with dual-reviewer consensus) | Low (stochastic API drift) | **High** (locked seeds, explicit prompt logging) |
| **Speed** | Slow (weeks/months) | Rapid (minutes) | **Moderate** (hours, due to validation/human-in-the-loop) |
| **Silent Drop Risk** | None (human errors are auditable) | Severe | **Mitigated** (guarded by automated recall testing) |
| **Documentation** | Hand-tracked spreadsheets | None | **Automated** (PRISMA-ready CSV output) |