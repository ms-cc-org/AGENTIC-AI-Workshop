# Learner Validation Protocol  
## Agentic AI Workshop — Notebooks 1 and 2

## Purpose

Thank you for helping validate the Agentic AI workshop.

Your role is to determine whether a participant with limited programming experience can open, understand, run, and complete the first two workshop notebooks without assistance from the notebook author.

This is not an assessment of you or the author. If something is confusing, fails, requires undocumented knowledge, or produces an unexpected result, that is useful validation evidence.

Please test the notebooks exactly as a workshop participant would encounter them.

## Materials under review

Repository:

https://github.com/ms-cc-org/AGENTIC-AI-Workshop

Notebooks:

1. `notebooks/01_chatbot_vs_agent.ipynb`
2. `notebooks/02_tool_using_agent.ipynb`

## Expected learner profile

Approach the notebooks as someone who:

- Has used an AI chatbot
- Has minimal Python experience
- Has little or no experience building AI agents
- Has a Google account
- Has not previously seen the notebook implementation
- May not have an OpenAI or Anthropic API key
- Expects to begin in mock mode without credentials

If your technical experience helps you overcome a problem, record that. A beginner may not be able to use the same workaround.

## Your responsibilities

You are responsible for:

- Following the instructions as written
- Running the notebooks from clean Google Colab sessions
- Recording unclear instructions and unexpected behavior
- Opening GitHub issues for reproducible problems
- Attaching useful, non-sensitive evidence
- Completing the final validation summary
- Retesting corrected issues when requested

You are not responsible for:

- Correcting notebook code
- Diagnosing every underlying cause
- Deciding whether the notebook author performed adequately
- Approving the notebooks for delivery
- Closing GitHub issues
- Using personal or sensitive data
- Paying for live-model API usage

## Important testing rules

During the primary learner pass:

- Start from a fresh Google Colab runtime.
- Follow only the README and notebook instructions.
- Complete cells in the order presented.
- Do not edit setup code unless explicitly instructed.
- Do not search the commit history for solutions.
- Do not contact the notebook author during the first pass.
- Record every point where you feel uncertain.
- Record instructions you must reinterpret or correct yourself.
- Record the approximate time required for each notebook.
- Record a problem before attempting a workaround.

A workaround does not convert a failed instruction into a successful one. Document both the original failure and the workaround.

## Data and credential restrictions

Use only the public or synthetic sample data included with the workshop.

Do not enter, upload, or transmit:

- Student records or grades
- Personally identifiable information
- Health or human-subject data
- Unpublished research
- Confidential peer-review material
- Personnel or financial records
- Institutional credentials
- Passwords or access tokens
- Restricted institutional documents
- Personal API keys unless explicitly authorized

Review screenshots before uploading them to GitHub. Remove credentials, personal information, browser tabs, email addresses, and unrelated institutional information.

---

# 1. Validation record

Complete this information before testing.

| Field | Response |
|---|---|
| Validator name | |
| Validation date | |
| Repository commit tested | |
| Browser | |
| Operating system | |
| Google Colab runtime/Python version | |
| Prior Python experience | None / Beginner / Intermediate / Advanced |
| Prior agent-development experience | None / Beginner / Intermediate / Advanced |
| Notebook 1 start time | |
| Notebook 1 finish time | |
| Notebook 2 start time | |
| Notebook 2 finish time | |

The commit hash is required. A notebook may change after testing, so findings must identify the exact version reviewed.

---

# 2. Reporting findings through GitHub

## Where to report problems

Open findings in the repository’s GitHub Issues section:

https://github.com/ms-cc-org/AGENTIC-AI-Workshop/issues

Use the **Learner validation finding** issue template when available.

## What should receive a separate issue

Open one issue for each distinct:

- Runtime failure
- Broken Colab or repository link
- Missing dependency
- Credential or provider-configuration problem
- Incorrect result
- Source-to-output discrepancy
- Tool-name or schema mismatch
- Exercise that cannot be completed
- Misleading technical explanation
- Missing data-transmission or privacy warning
- Problem that prevents a stated learning outcome

## What may be consolidated

Use one consolidated issue per notebook for:

- Spelling
- Grammar
- Formatting
- Minor clarity problems
- Inconsistent capitalization
- Small terminology inconsistencies

Do not create a separate issue for every typo.

## Avoid duplicates

Before opening an issue:

1. Review the current open issues.
2. If the same problem already exists, add a comment with your evidence.
3. Include the commit and environment you tested.
4. Do not open a duplicate unless the behavior is materially different.

## Issue ownership and closure

The validator documents findings but does not close issues.

The process is:

```text
Validator reports finding
        ↓
Project manager reviews and labels it
        ↓
Notebook author submits correction
        ↓
Author attaches test evidence
        ↓
Technical reviewer verifies correction
        ↓
Learner retests when needed
        ↓
Project manager closes issue
```

Do not close an issue after a correction appears. A correction must first be verified against the issue’s acceptance criteria.

## Severity levels

### Blocker

You cannot continue or complete a required notebook outcome.

Examples:

- A required cell fails.
- The notebook requires an undocumented credential.
- A dependency is unavailable.
- A tool call cannot complete.
- The exercise cannot be run.

### High

You can continue, but a major result or explanation is incorrect, misleading, unsafe, or unusable.

Examples:

- The explanation contradicts the code.
- A mock answer does not match its source.
- Scripted behavior is described as a model decision.
- Retrieved institutional data could be transmitted without warning.

### Medium

You can continue, but the issue causes substantial confusion or unnecessary troubleshooting.

Examples:

- Prerequisites are unclear.
- An instruction appears in the wrong place.
- The exercise requires knowledge that was not taught.
- An error is caught but not explained.

### Low

The issue does not prevent learning but should be corrected.

Examples:

- Spelling or grammar
- Inconsistent terminology
- Awkward formatting
- Minor readability problems

The project manager may adjust severity during triage.

## GitHub issue format

Use this format if no issue template appears:

```markdown
## Notebook

- [ ] Notebook 1
- [ ] Notebook 2
- [ ] Repository or setup instructions

## Finding summary

Describe one specific problem.

## Severity

- [ ] Blocker
- [ ] High
- [ ] Medium
- [ ] Low

## Version tested

- Commit:
- Validation date:
- Browser:
- Operating system:
- Colab/Python version:
- Provider: Mock / OpenAI / Anthropic / Not applicable
- Model, if applicable:

## Location

- Section heading:
- Cell or nearby text:

## Steps to reproduce

1.
2.
3.

## Expected result

What did the instructions lead you to expect?

## Actual result

What happened? Include the complete error when applicable.

## Evidence

Attach a screenshot, cell output, or tool-call transcript. Remove credentials
and sensitive information before uploading.

## Workaround

- [ ] I did not find a workaround.
- [ ] I found this workaround:

## Learner impact

How did this affect your ability to understand or complete the lesson?

## Suggested improvement

Optional.

## Closure policy

The learner-validator documents findings but does not close validation issues.
The designated reviewer will verify corrections and close the issue.
```

---

# 3. Repository onboarding review

Starting from the repository home page, determine whether you can answer:

- [ ] What is the workshop about?
- [ ] Who is the intended audience?
- [ ] What will participants learn?
- [ ] What will participants build?
- [ ] What prerequisites are required?
- [ ] Can participants begin without an API key?
- [ ] Which notebook should be opened first?
- [ ] Is there a visible Colab link?
- [ ] Are data-use limitations stated?
- [ ] Is the workshop’s development status clear?

Record brief notes:

```text
Repository onboarding notes:
```

Open a GitHub issue if a missing or incorrect instruction could prevent a participant from beginning.

---

# 4. Notebook 1 validation  
## Chatbot vs. Agent

## Intended learner outcome

After Notebook 1, a participant should be able to:

- Explain chatbot versus workflow versus agent
- Identify the model, loop, tools, state or memory, and stopping condition
- Explain what the tool-using system does differently
- Recognize that mock-mode actions are scripted
- Decide when a workflow may be preferable to an agent

## 4.1 Open the notebook

- [ ] Open Notebook 1 from the repository.
- [ ] Use the “Open in Colab” badge.
- [ ] Confirm that the expected notebook opens.
- [ ] Confirm that the title and purpose are clear.
- [ ] Confirm that prerequisites appear before setup.

## 4.2 Prepare a clean runtime

1. Select **Runtime → Disconnect and delete runtime**, if available.
2. Reconnect to obtain a fresh runtime.
3. Do not add API credentials.
4. Confirm that the notebook defaults to:

```python
PROVIDER = "mock"
```

Verify:

- [ ] Mock mode is the default.
- [ ] The notebook says no API key is required.
- [ ] No instruction asks you to paste a key into a code cell.
- [ ] Mock and live-provider behavior are distinguished.

## 4.3 Run the setup

Run the setup cell exactly as written.

Verify:

- [ ] Package installation completes.
- [ ] The cell completes without an exception.
- [ ] The output identifies `PROVIDER='mock'`.
- [ ] The explanation is understandable.
- [ ] You know which code is central to the lesson.
- [ ] You know which code can be treated as reusable infrastructure.

If the cell fails, open a Blocker issue and attach the complete error.

## 4.4 Run the chatbot example

Before running it, write your prediction:

```text
My prediction:
```

Verify:

- [ ] The chatbot cell completes.
- [ ] The response summarizes papers A, B, and C.
- [ ] The response does not describe unrelated papers.
- [ ] Methods and metrics match the supplied abstracts.
- [ ] The notebook accurately says that the chatbot uses supplied context.
- [ ] The notebook does not claim that this chatbot must guess despite having the abstracts.

Expected source values:

| Paper | Expected information |
|---|---|
| A | TSR 89.4%; ATR from 6.4 to 4.2; hallucination rate reduced by 38% |
| B | WAI increased by 22%; compliance improved by 15.8% |
| C | Latency reduced 4.1×; cloud cost reduced by 73.2%; retained 94.6% accuracy |

Open a separate issue for any substantive source-to-output discrepancy.

## 4.5 Understand the agent loop

Determine whether you can identify:

- [ ] Where the user task is stored
- [ ] Where the model is called
- [ ] How a tool request is detected
- [ ] Where the tool function runs
- [ ] How the result returns to the model
- [ ] How the loop stops
- [ ] What `max_steps` does
- [ ] What happens when a tool fails

Describe the loop:

```text
My explanation:
```

## 4.6 Run the paper-reading agent

Verify:

- [ ] The function and registered tool use the same name.
- [ ] Mock calls use the registered name.
- [ ] Transcript code uses the registered name.
- [ ] The agent calls the tool for A, B, and C.
- [ ] Each tool result contains the correct abstract.
- [ ] No unknown-tool error occurs.
- [ ] A comparison table appears.

Record the observed sequence:

```text
Observed tool calls:
```

## 4.7 Verify the comparison

- [ ] Every row corresponds to the correct paper.
- [ ] Numerical values match the abstracts.
- [ ] Methods and limitations are supported.
- [ ] No unrelated claims appear.
- [ ] The table is readable.
- [ ] Mock calls are identified as scripted.
- [ ] The notebook does not claim the agent chose a format required by the prompt.

## 4.8 Evaluate the conceptual comparison

Answer:

```text
What did the chatbot do?

What did the agent do?

What information was supplied to each?

Which actions were scripted in mock mode?

Which decisions would be made by a live model?

When would a predefined workflow be preferable?
```

Rate each statement from 1 to 5:

| Statement | Rating |
|---|---|
| I can explain chatbot versus agent | |
| I can explain workflow versus agent | |
| The example supports the claims made about it | |
| I could explain this to a colleague | |

## 4.9 Complete the paper D exercise

- [ ] Add paper D.
- [ ] Update the required mock behavior.
- [ ] Run the review with A, B, C, and D.
- [ ] Confirm that D appears in the tool calls.
- [ ] Confirm that D appears in the final answer.
- [ ] Rerun the exercise.
- [ ] Confirm that stale or duplicate state does not appear.

Record:

```text
Time required:

Instructions that were unclear:

Errors encountered:

Help I would have needed:

What I learned:
```

## 4.10 Restart and run all

1. Restart the Colab session.
2. Run all cells from the beginning.
3. Do not reuse state from the previous session.

Verify:

- [ ] The notebook completes.
- [ ] Outputs appear in the expected order.
- [ ] No hidden state is required.
- [ ] The exercise remains usable.
- [ ] No manual cleanup is required.

## 4.11 Notebook 1 assessment

Rate from 1 to 5:

| Statement | Rating |
|---|---|
| Prerequisites were clear | |
| Setup was easy to follow | |
| The amount of code was appropriate | |
| The chatbot example was accurate | |
| The agent example was accurate | |
| The exercise was achievable | |
| I understand the main concept | |
| I could complete this without an instructor | |

```text
Most helpful part:

Most confusing part:

One thing I would remove:

One thing I would add:

Ready for a beginner workshop? Yes / No

Reason:
```

---

# 5. Notebook 2 validation  
## Tool-Using Agent

## Intended learner outcome

After Notebook 2, a participant should be able to:

- Explain the function/schema distinction
- Distinguish web search from local retrieval
- Explain validated structured tool arguments
- Understand model-selected versus scripted tool calls
- Build or modify a simple tool

## 5.1 Open Notebook 2 independently

Begin in a new Colab session.

Verify:

- [ ] The repository link works.
- [ ] The notebook purpose is clear.
- [ ] Prerequisites are clear.
- [ ] It can begin without state from Notebook 1.
- [ ] Mock mode is the default.
- [ ] No API key is required.

## 5.2 Run setup

Verify:

- [ ] `openai` installs.
- [ ] `anthropic` installs.
- [ ] `ddgs` installs.
- [ ] `tavily-python` installs if documented.
- [ ] The repository is cloned into the expected location.
- [ ] Rerunning setup does not create a nested repository.
- [ ] The notebook ends in the correct directory.
- [ ] `OPENAI_API_KEY` is used consistently.
- [ ] `ANTHROPIC_API_KEY` is used consistently.

Open a Blocker issue for a clean-runtime setup failure.

## 5.3 Explain a tool

Complete:

```text
A tool function is:

A tool schema is:

The model uses the schema to:

The application uses the function to:
```

Verify that the notebook explains the distinction before asking you to build a tool.

## 5.4 Test web search

In mock mode:

- [ ] The notebook does not unexpectedly perform a live search.
- [ ] It tells you when external network access will occur.
- [ ] Missing network access produces a useful message.
- [ ] Missing optional credentials do not stop the notebook.

If live search is authorized:

- [ ] Results include titles.
- [ ] Results include URLs.
- [ ] Results include snippets.
- [ ] The search provider is identifiable.
- [ ] The notebook tells learners to verify the original source.

## 5.5 Test local retrieval

- [ ] The dataset directory is found.
- [ ] Expected files are listed.
- [ ] Files load without an exception.
- [ ] The sample query returns a relevant result.
- [ ] The excerpt contains the relevant matched text.
- [ ] The source filename is visible.
- [ ] Keyword-search limitations are explained.
- [ ] The same query returns the same result on rerun.

Test:

| Query | Expected result |
|---|---|
| `AI funding deadline proposal` | Relevant funding document |
| Clearly unrelated phrase | No-match response |
| A synonym absent from the source | Keyword limitation becomes visible |

## 5.6 Test the grant-record tool

- [ ] The good record is accepted.
- [ ] The bad record is rejected.
- [ ] Rejection reasons are understandable.
- [ ] Date requirements are clear.
- [ ] Amount requirements are clear.
- [ ] Example arguments match the registered schema.
- [ ] Numeric fields receive numeric values.
- [ ] The terminology distinguishes tool arguments from provider-level structured responses.

## 5.7 Test tool routing

| Task | Expected tool | Observed tool | Correct? |
|---|---|---|---|
| Current public information | `search_web` | | |
| Local-document question | `retrieve_docs` | | |
| Save grant details | `record_grant` | | |

Verify:

- [ ] Every registered tool is demonstrated.
- [ ] The selected tool is displayed.
- [ ] Mock selections are identified as scripted.
- [ ] Live-provider selections are identified as model-selected.
- [ ] Tool arguments match their schemas.
- [ ] Tool failures are visible.

## 5.8 Verify the data warning

Before live-provider use, confirm that the notebook explains:

- [ ] Local retrieval does not necessarily mean local processing.
- [ ] Retrieved passages may be transmitted to the provider.
- [ ] Only approved data should be used.
- [ ] Keys belong in Colab Secrets.
- [ ] Search and model outputs require verification.

A missing warning should be reported as High severity.

## 5.9 Complete the tool-building exercise

- [ ] Complete the function.
- [ ] Understand the return value.
- [ ] Create or modify the schema.
- [ ] Register the tool.
- [ ] Create a mock call.
- [ ] Run the agent.
- [ ] Interpret the output.
- [ ] Locate a hint or solution if blocked.

Record:

```text
Tool selected:

Time required:

Steps completed without help:

Steps requiring help:

Errors encountered:

What I learned:
```

Rate difficulty:

- [ ] Too easy
- [ ] Appropriate
- [ ] Challenging but achievable
- [ ] Too difficult for the audience
- [ ] Could not complete

## 5.10 Restart and run all

- [ ] Setup completes.
- [ ] Mock mode completes without credentials.
- [ ] No prior runtime state is required.
- [ ] Tools are not registered multiple times.
- [ ] The corpus loads correctly.
- [ ] The agent demonstration completes.
- [ ] The exercise remains usable.
- [ ] No manual directory cleanup is needed.

## 5.11 Notebook 2 assessment

Rate from 1 to 5:

| Statement | Rating |
|---|---|
| Prerequisites were clear | |
| Setup was easy to follow | |
| Tool explanations were understandable | |
| Web search was demonstrated accurately | |
| Document retrieval was demonstrated accurately | |
| Structured tool arguments were explained accurately | |
| Mock versus live behavior was clear | |
| The exercise was achievable | |
| I could complete this without an instructor | |

```text
Most helpful part:

Most confusing part:

One thing I would remove:

One thing I would add:

Ready for a beginner workshop? Yes / No

Reason:
```

---

# 6. Optional live-provider validation

Complete this section only if an approved test account, API key, and budget have been provided.

Do not use personal or institutional data.

For each provider, record:

| Field | Response |
|---|---|
| Provider | |
| Model | |
| Commit | |
| Test account approved by | |
| Notebook 1 result | Pass / Fail |
| Notebook 2 result | Pass / Fail |
| Approximate calls or cost | |
| Errors or warnings | |

Verify:

- [ ] The documented secret name works.
- [ ] No key appears in output.
- [ ] The model is available.
- [ ] Tool calls match their schemas.
- [ ] The expected task completes.
- [ ] Model variability is acknowledged.
- [ ] Retrieved content is transmitted only when approved.

---

# 7. Final validation summary

## Results

| Component | Result |
|---|---|
| Repository onboarding | Pass / Pass with findings / Fail |
| Notebook 1 mock run | Pass / Pass with findings / Fail |
| Notebook 1 exercise | Pass / Pass with findings / Fail |
| Notebook 1 clean rerun | Pass / Pass with findings / Fail |
| Notebook 2 mock run | Pass / Pass with findings / Fail |
| Notebook 2 exercise | Pass / Pass with findings / Fail |
| Notebook 2 clean rerun | Pass / Pass with findings / Fail |
| Live providers, if authorized | Pass / Fail / Not tested |

## GitHub findings

| Issue number | Short title | Severity | Notebook |
|---|---|---|---|
| | | | |

## Findings count

| Severity | Count |
|---|---:|
| Blocker | |
| High | |
| Medium | |
| Low | |

## Recommendation

Select one:

- [ ] Ready for workshop delivery
- [ ] Ready after minor corrections
- [ ] Requires correction and another validation cycle
- [ ] Not ready for the intended audience

## Summary

```text
What worked well:

What prevented or disrupted completion:

What was confusing:

What required undocumented knowledge:

Did Notebook 1 meet its learning outcome?

Did Notebook 2 meet its learning outcome?

Recommended next action:
```

## Validator acknowledgment

```text
I tested the commit identified in this document using the process above. This
report reflects my experience following the repository and notebooks as
written. I have not closed any validation issues.

Validator:

Date:
```

# After validation

Submit this completed report to the project manager.

The notebook author will:

1. Review accepted findings.
2. Submit corrections.
3. Link the corrective commit or pull request.
4. Attach author-test evidence.
5. Return the notebook for retesting when required.

The project manager or designated technical reviewer will verify the corrections and close the GitHub issues.
