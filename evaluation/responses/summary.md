# Evaluation Summary

## Test Configuration
- **Model tested:** [e.g. GPT-4o / Claude Sonnet / Gemini Pro]
- **Date:** [YYYY-MM-DD]
- **Evaluator(s):** [names]
- **Blind evaluation:** [Yes/No — did the evaluator know which response had context?]

---

## Aggregate Results

### Overall Scores

| Scenario | Prompt A (Baseline) | Prompt B (Assisted) | Delta | Preferred |
|----------|-------------------|-------------------|-------|-----------|
| 1. Executive tribunal | /5 | /5 | | A / B |
| 2. Food safety crisis | /5 | /5 | | A / B |
| 3. Debt company forums | /5 | /5 | | A / B |
| **Average** | **/5** | **/5** | **+/-** | |

### By Criterion (averaged across all 3 scenarios)

| Criterion | Prompt A Avg | Prompt B Avg | Delta |
|-----------|-------------|-------------|-------|
| Relevance | /5 | /5 | |
| Groundedness | /5 | /5 | |
| Actionability | /5 | /5 | |
| Risk Awareness | /5 | /5 | |
| Accuracy | /5 | /5 | |
| Trust | /5 | /5 | |

### Preference Rate

- Archive-assisted preferred in **X/3** scenarios
- Baseline preferred in **X/3** scenarios
- No clear preference in **X/3** scenarios

---

## Success Criteria Assessment

From AGENTS.md:
- **Target:** >=70% preference for archive-assisted responses → **Met / Not Met**
- **Improved groundedness and actionability scores** → **Met / Not Met**
- **Reduced unsupported claims** → **Met / Not Met**

---

## Key Findings

### Where archive context helped most
1. 
2. 
3. 

### Where archive context helped least (or didn't help)
1. 
2. 
3. 

### Most impactful context file types
- [ ] Case studies (CS) — real precedents with metrics
- [ ] Scenarios (S) — situation framing
- [ ] Actions (A) — strategic decision trees
- [ ] How-To guides (H) — step-by-step procedures

### Common baseline weaknesses
_What did the model consistently get wrong or miss without context?_
- 
- 
- 

### Common archive-assisted strengths
_What did the model consistently do better with context?_
- 
- 
- 

---

## Hallucination Analysis

| Scenario | Prompt A Hallucinations | Prompt B Hallucinations |
|----------|------------------------|------------------------|
| 1 | [count and describe] | [count and describe] |
| 2 | [count and describe] | [count and describe] |
| 3 | [count and describe] | [count and describe] |

---

## Decision Gate

Based on AGENTS.md Step 6:

### If Positive (>=70% preference, meaningful score improvement):
- [ ] Proceed to embeddings and vector DB
- [ ] Priority context types to embed first: _______________
- [ ] Estimated corpus size: 65 files, ~71,000 words

### If Mixed (some improvement, inconsistent):
- [ ] Improve case study structuring — which ones need work?
- [ ] Refine prompts — what prompt patterns work best?
- [ ] Add more context files in areas where gaps appeared

### If Negative (no meaningful improvement):
- [ ] Reassess data quality — which files were unhelpful?
- [ ] Identify missing patterns — what knowledge is absent?
- [ ] Consider whether the model already knows this domain well enough

---

## Recommendations for Next Steps
1. 
2. 
3. 

---

## Raw Data Location
- Scenario definitions: `evaluation/scenarios.md`
- Individual response files: `evaluation/responses/scenario-{1,2,3}-prompt-{a,b}-*.md`
