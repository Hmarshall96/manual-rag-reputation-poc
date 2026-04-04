# 📁 RAG Pilot Evaluation Pack

This document contains multiple markdown files you can split into your project.

---

# 📄 agents.md

## Project Overview

This project aims to evaluate whether a curated archive of consultancy materials (Excel, Word, PDF) can improve the quality of AI-generated recommendations for online reputation management.

The approach uses a **manual Retrieval-Augmented Generation (RAG) simulation** to test value before investing in full infrastructure.

---

## Objectives

- Determine whether archive data improves:
  - Groundedness of responses
  - Quality of reasoning
  - Actionability of recommendations
  - Risk-aware decision making

- Provide evidence to support or reject investment in:
  - Embeddings
  - Vector databases
  - Automated retrieval pipelines

---

## Key Hypothesis

Providing structured case studies and best practices from the archive will result in **more useful, defensible, and context-aware recommendations** compared to baseline LLM responses.

---

## Evaluation Approach

- Manual retrieval (no vector DB)
- Side-by-side comparison:
  - Baseline (no context)
  - Archive-assisted (with curated context)
- Blind human evaluation

---

## Success Criteria

- ≥70% preference for archive-assisted responses
- Improved groundedness and actionability scores
- Reduced unsupported claims

---

## Important Principles

- We are testing **data value**, not model intelligence
- Retrieval is simulated manually
- Results are directional, not final proof

---

# 📄 01_case_extraction.md

## Step 1 — Extract and Structure Case Knowledge

### Purpose

Convert raw consultancy files into structured, reusable knowledge units that can be injected into prompts.

---

### Why This Matters

Raw documents are:
- Noisy
- Inconsistent
- Poorly suited for direct model reasoning

Structured cases provide:
- Clear patterns
- Reusable insights
- Better grounding for AI outputs

---

### Extraction Process

For each document:

1. Read and identify relevant cases or insights
2. Extract key elements
3. Convert into structured markdown

---

### Required Fields

- Case Summary
- Issue Type
- Context
- Actions Taken
- Outcome
- Lessons Learned
- Key Risks / Trade-offs

---

### Example

```markdown
# Case: Review Platform Crisis

## Context
Sudden spike in negative reviews following product update

## Issue Type
Customer backlash / review platform

## Actions Taken
- Public response issued
- Direct customer outreach
- Product rollback communication

## Outcome
Review sentiment stabilised within 5 days

## Lessons Learned
- Respond quickly and visibly
- Combine public + private responses
```

---

### Best Practice Documents

Also create standalone guides such as:

- Handling misinformation
- Responding to journalists
- Crisis escalation playbooks

---

### Output

A folder of clean markdown files representing:
- Case studies
- Best practices

---

# 📄 02_scenarios.md

## Step 2 — Define Evaluation Scenarios

### Goal

Create realistic prompts to test model performance.

---

### Requirements

Each scenario should include:
- Situation description
- Key challenge
- Desired response characteristics

---

### Example

```markdown
Scenario: Executive Reputation Issue

An executive is facing criticism after an old article resurfaced online and is gaining traction.
```

---

### Coverage

- Easy (clear solution)
- Medium (some ambiguity)
- Hard (conflicting signals)

---

### Target

8–15 scenarios

---

# 📄 03_experiment.md

## Step 3 — Run Controlled Comparisons

### Setup

For each scenario, generate two outputs:

---

### A. Baseline

- Prompt only
- No archive context

---

### B. Archive-Assisted

- Same prompt
- Add 1–3 relevant case summaries

---

### Optional C. Generic Guidance

- Prompt + general best practices

---

### Key Principle

Keep everything identical except the context.

---

# 📄 04_evaluation.md

## Step 4 — Blind Evaluation

### Process

- Remove labels from outputs
- Present side-by-side
- Reviewers score independently

---

### Scoring Criteria

| Criterion          | Description |
|-------------------|------------|
| Relevance         | Addresses the issue |
| Reasoning         | Logical structure |
| Risk Awareness    | Appropriate caution |
| Actionability     | Practical steps |
| Groundedness      | Uses provided context |
| Accuracy          | No hallucinations |

---

### Scale

1 = Poor
3 = Adequate
5 = Excellent

---

### Additional Question

Which answer would you use?

---

# 📄 05_analysis.md

## Step 5 — Analyse Results

### Metrics

- Preference rate
- Average score per criterion
- Score improvement

---

### Example Output

```markdown
- Archive-assisted preferred in 8/10 cases
- Groundedness: 2.9 → 4.3
- Actionability: 3.2 → 4.4
```

---

### Key Insights

- Where does archive help most?
- Where does it not help?

---

# 📄 06_decision.md

## Step 6 — Decision Gate

### If Positive

Proceed to:
- Embeddings
- Vector DB
- Retrieval system

---

### If Mixed

- Improve case structuring
- Refine prompts

---

### If Negative

- Reassess data quality
- Identify missing patterns

---

## Final Principle

We are proving:

> The model performs better when grounded in our data

Not:

> The model is inherently smarter

---

# ✅ End of Pack

Split this document into separate markdown files as needed.

