# Technical Concept Note (SYNTHETIC): Grounding, Hallucination, and Faithfulness in RAG

> **Core Concept:** Retrieval-Augmented Generation (RAG) shifts an LLM's role from a *knowledge retrieval engine* (relying on its internal parametric memory) to a *reasoning engine* (relying on external, non-parametric source passages). While RAG drastically reduces hallucination rates, grounding does not equal absolute truth.

---

## 1. The RAG Paradox: Why Grounded Models Still Hallucinate

Injecting retrieved context into a model's prompt reduces the need for the model to "memorize" facts. However, even with 100% accurate search retrieval, generative models can still fail during the synthesis phase.

These failures generally fall into three categories:

* **Context Blending:** The model inappropriately merges facts from two disparate source passages, creating a false synthesis.
* **Reading Comprehension Errors:** The model misinterprets syntactic relationships (e.g., reversing subject-object relations or confusing negation) within a highly technical passage.
* **Parametric Leakage:** The model ignores the provided context and defaults back to its pre-trained parametric knowledge when discussing highly familiar topics.

---

## 2. Practical Guardrails for Grounded Generation

To transition a RAG system from "suggestive" to "deterministic," engineers must implement structured prompt constraints and runtime guardrails.

```
[Retrieved Passages] ──> [Strict System Prompt Constraints] ──> [Deterministic Claim Citation] ──> [Refusal Fallback]

```

* **Closed-Book Constraint:** Explicitly instruct the model that its "world" is strictly limited to the provided context.
> *Example Prompt Guard:* "You are a strict reading comprehension assistant. Answer the query using ONLY the facts explicitly mentioned in the context below. If the answer cannot be directly derived from the context, you must state 'I do not have enough information to answer.'"


* **Granular Citation (Source-ID Attribution):** Force the model to attach a verifiable source key (such as a passage ID, database key, or page number) to every assertion it makes.
> *Example Output Format:* "The fiscal year 2025 budget increased by 4% `[Source: Doc_B, Page 12]`, primarily driven by research infrastructure investments `[Source: Doc_A, Page 3]`."


* **Strict Refusal Mechanisms:** Programmatically detect and validate refusal states. If the retriever fails to find relevant passages, the generation step must be bypassed entirely or forced to return a standard "No relevant sources found" error code rather than letting the model attempt to extrapolate.

---

## 3. Evaluation Metrics: Faithfulness vs. Fluency

When auditing RAG performance, standard text-similarity metrics (like ROUGE or BLEU) are insufficient because they measure *fluency* and *n-gram overlap* rather than *factual truth*.

Instead, the industry prioritizes **Faithfulness**—the degree to which the generated response is strictly derived from the retrieved context.

### Mathematical Formulation of Faithfulness

To evaluate Faithfulness ($F$) programmatically:

1. Extract the set of individual, atomic claims $C = \{c_1, c_2, \dots, c_n\}$ from the generated answer $A$ using an NLI (Natural Language Inference) model or an LLM parser.
2. Let $S = \{s_1, s_2, \dots, s_m\}$ represent the retrieved source passages.
3. Define an entailment function $g(c_i, S) \in \{0, 1\}$, where:

$$g(c_i, S) = \begin{cases} 1 & \text{if } c_i \text{ is logically entailed by } S \\ 0 & \text{otherwise} \end{cases}$$



The overall Faithfulness score is calculated as the ratio of supported claims to total claims:

$$F = \frac{\sum_{i=1}^{n} g(c_i, S)}{n}$$

---

### Core Metric Comparison

| Evaluation Metric | What it Measures | How it's Checked | Failure Mode Detected |
| --- | --- | --- | --- |
| **Faithfulness (Grounding)** | Is the response fully supported *only* by the retrieved context? | Entailment check against the source text ($F \to 1.0$). | **Hallucination / Fabrication** (The model made up a fact not in the context). |
| **Answer Relevance** | Does the response actually address the user's initial query? | Semantic similarity between the user's question and the model's answer. | **Topic Drift** (The model answered a different question using the correct context). |
| **Fluency** | Is the output grammatically correct, coherent, and natural? | Perplexity scores, standard language modeling evaluations. | **Gibberish / Degradation** (The model is factual but illegible). |