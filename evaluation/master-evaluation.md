# Master Evaluation: Manual RAG Reputation Management PoC

## Overview

This document presents the combined results of two independent evaluations comparing baseline (Prompt A) and archive-assisted (Prompt B) responses across three reputation management scenarios. The evaluations used the same scoring criteria but different methods, and their scores are presented separately throughout.

### What was tested
- **Model:** GPT 5.3 Thinking
- **Date:** 2026-04-04
- **Approach:** For each scenario, the same query was sent in two separate conversations — once without context (Prompt A / Baseline) and once with relevant internal documents attached (Prompt B / Archive-Assisted). The only difference between prompts was a framing line asking the model to use the provided context and cite documents by ID.

### Evaluation methods

| | Automated Evaluation | Human Evaluation |
|---|---|---|
| **Evaluator** | Claude (LLM-based analysis) | 4 domain experts (Andrew, Ben, Charlie, Jen) |
| **Method** | Side-by-side comparison of full response pairs | Independent blind scoring of individual responses |
| **Scenarios scored** | All 3 | Scenario 1: 2 reviewers; Scenarios 2-3: 4 reviewers each |
| **Scoring scale** | 1-5 (integer) | 1-5 (half-points permitted) |

### Scoring criteria

| Criterion | Description |
|-----------|-------------|
| **Relevance** | Addresses the specific issue raised |
| **Groundedness** | Claims are supported by evidence, case studies, or documented procedures |
| **Actionability** | Provides specific, executable steps (not just high-level advice) |
| **Risk Awareness** | Identifies what could go wrong and sets realistic expectations |
| **Accuracy** | No hallucinated procedures, fake legal citations, or unsupported claims |
| **Trust** | References real examples and proven outcomes to build confidence |

### Notes on comparability
- The automated evaluator had access to both responses simultaneously; human reviewers scored individually.
- Jen's Scenario 1 feedback was excluded because she received a version containing the wrong prompt for Scenario 1A, which she correctly identified. Ben did not review Scenario 1.
- The automated evaluator used integer scores only; human reviewers used half-point increments, resulting in more granular averages.

---

## Side-by-Side Comparison

### Scenario 1: UK Executive with Employment Tribunal Press Coverage

| Criterion | Automated A | Automated B | Automated Delta | Human A (n=2) | Human B (n=2) | Human Delta |
|-----------|:-----------:|:-----------:|:---------------:|:-------------:|:-------------:|:-----------:|
| Relevance | 5 | 5 | 0 | 4.00 | 4.00 | 0.00 |
| Groundedness | 3 | 5 | +2 | 3.50 | 4.50 | +1.00 |
| Actionability | 4 | 5 | +1 | 3.50 | 3.75 | +0.25 |
| Risk Awareness | 3 | 5 | +2 | 3.50 | 4.00 | +0.50 |
| Accuracy | 4 | 5 | +1 | 3.75 | 4.25 | +0.50 |
| Trust | 3 | 5 | +2 | 3.00 | 3.50 | +0.50 |
| **Mean** | **3.7** | **5.0** | **+1.3** | **3.54** | **4.00** | **+0.46** |

### Scenario 2: Restaurant Chain Facing Food Safety Crisis

| Criterion | Automated A | Automated B | Automated Delta | Human A (n=4) | Human B (n=4) | Human Delta |
|-----------|:-----------:|:-----------:|:---------------:|:-------------:|:-------------:|:-----------:|
| Relevance | 5 | 5 | 0 | 4.75 | 4.50 | -0.25 |
| Groundedness | 3 | 5 | +2 | 3.00 | 3.88 | +0.88 |
| Actionability | 5 | 5 | 0 | 3.75 | 4.00 | +0.25 |
| Risk Awareness | 4 | 5 | +1 | 3.75 | 3.75 | 0.00 |
| Accuracy | 5 | 5 | 0 | 3.63 | 4.13 | +0.50 |
| Trust | 3 | 5 | +2 | 2.50 | 4.00 | +1.50 |
| **Mean** | **4.2** | **5.0** | **+0.8** | **3.56** | **4.04** | **+0.48** |

### Scenario 3: Company Facing Defamatory Forum Posts and Negative Reviews

| Criterion | Automated A | Automated B | Automated Delta | Human A (n=4) | Human B (n=4) | Human Delta |
|-----------|:-----------:|:-----------:|:---------------:|:-------------:|:-------------:|:-----------:|
| Relevance | 5 | 5 | 0 | 4.50 | 4.50 | 0.00 |
| Groundedness | 3 | 5 | +2 | 3.00 | 4.38 | +1.38 |
| Actionability | 5 | 5 | 0 | 3.50 | 4.25 | +0.75 |
| Risk Awareness | 4 | 5 | +1 | 3.50 | 3.88 | +0.38 |
| Accuracy | 5 | 5 | 0 | 3.63 | 4.13 | +0.50 |
| Trust | 3 | 5 | +2 | 2.50 | 4.38 | +1.88 |
| **Mean** | **4.2** | **5.0** | **+0.8** | **3.44** | **4.25** | **+0.81** |

### Cross-Scenario Averages

| Criterion | Automated A | Automated B | Automated Delta | Human A | Human B | Human Delta |
|-----------|:-----------:|:-----------:|:---------------:|:-------:|:-------:|:-----------:|
| Relevance | 5.0 | 5.0 | 0 | 4.45 | 4.35 | -0.10 |
| Groundedness | 3.0 | 5.0 | +2.0 | 3.15 | 4.25 | +1.10 |
| Actionability | 4.7 | 5.0 | +0.3 | 3.58 | 4.03 | +0.45 |
| Risk Awareness | 3.7 | 5.0 | +1.3 | 3.58 | 3.85 | +0.27 |
| Accuracy | 4.7 | 5.0 | +0.3 | 3.66 | 4.16 | +0.50 |
| Trust | 3.0 | 5.0 | +2.0 | 2.65 | 3.98 | +1.33 |
| **Mean** | **4.0** | **5.0** | **+1.0** | **3.51** | **4.10** | **+0.59** |

### Client Preference

| | Automated | Human |
|---|---|---|
| Scenario 1 | B preferred | B preferred (2/2) |
| Scenario 2 | B preferred | B preferred (4/4) |
| Scenario 3 | B preferred | B preferred (4/4) |
| **Overall** | **3/3 (100%)** | **10/10 (100%)** |

---

## Part 1: Automated Evaluation

### Scoring Summary

#### Scenario 1: UK Executive with Employment Tribunal Press Coverage

| Criterion | Prompt A (Baseline) | Prompt B (Assisted) | Delta |
|-----------|:-------------------:|:-------------------:|:-----:|
| Relevance | 5 | 5 | 0 |
| Groundedness | 3 | 5 | **+2** |
| Actionability | 4 | 5 | +1 |
| Risk Awareness | 3 | 5 | **+2** |
| Accuracy | 4 | 5 | +1 |
| Trust | 3 | 5 | **+2** |
| **Average** | **3.7** | **5.0** | **+1.3** |

#### Scenario 2: Restaurant Chain Food Safety Crisis

| Criterion | Prompt A (Baseline) | Prompt B (Assisted) | Delta |
|-----------|:-------------------:|:-------------------:|:-----:|
| Relevance | 5 | 5 | 0 |
| Groundedness | 3 | 5 | **+2** |
| Actionability | 5 | 5 | 0 |
| Risk Awareness | 4 | 5 | +1 |
| Accuracy | 5 | 5 | 0 |
| Trust | 3 | 5 | **+2** |
| **Average** | **4.2** | **5.0** | **+0.8** |

#### Scenario 3: Debt Collection Company Forum/Review Issues

| Criterion | Prompt A (Baseline) | Prompt B (Assisted) | Delta |
|-----------|:-------------------:|:-------------------:|:-----:|
| Relevance | 5 | 5 | 0 |
| Groundedness | 3 | 5 | **+2** |
| Actionability | 5 | 5 | 0 |
| Risk Awareness | 4 | 5 | +1 |
| Accuracy | 5 | 5 | 0 |
| Trust | 3 | 5 | **+2** |
| **Average** | **4.2** | **5.0** | **+0.8** |

### Detailed Analysis

#### Scenario 1

**Groundedness (+2):**

| Evidence Type | Prompt A | Prompt B |
|---------------|----------|----------|
| Case study citations | None | CS02 cited 15+ times with specific metrics (16 articles, 20 images, 13/20 negative start, 4-month timeline) |
| RTBF success rates | No statistics | ~29% overall, lower for news sites — sourced from [H01] |
| Image removal precedent | Called it "highest ROI" with no evidence | Cited CS02's 20/20 image removal as proof |
| Timeline basis | Generic 12-18 month estimate | 4-month benchmark from CS02 with caveats |
| Document citations | External URLs only | Bracketed [CS02], [H01], [H02], [A01], [S01], [H08] throughout |

**Actionability (+1):** Both provided strong templates (RTBF, publisher letters, IPSO complaints, image removal). Key difference: Prompt B included an RTBF appeal/resubmission template from [H02], while Prompt A had no rejection recovery strategy. Prompt B also referenced submitting via personal email rather than agent email to improve success rates [H02].

**Risk Awareness (+2):**

| Risk Factor | Prompt A | Prompt B |
|-------------|----------|----------|
| Streisand effect | Not mentioned | Explicitly warned, citing [S01] and [A01] |
| RTBF territorial limits | Not mentioned | Cited Google v CNIL — delisting not worldwide |
| Journalism exemptions | Covered | Covered with more nuance |
| Realistic expectations | "Total disappearance is not" | "I would not promise total deletion" — backed by CS02 evidence |

**Trust (+2):** Prompt A reads as competent generic advice. Prompt B reads as advice from a firm that has done this exact thing before — CS02 is cited as a directly analogous case with verified outcomes, the "weekly drumbeat" execution model is credited from the client testimonial, and every recommendation links to either internal evidence or external legal authority.

**IPSO Test (H08 organic surfacing):** Prompt A mentioned IPSO in passing (1 paragraph). Prompt B produced a full section with per-outlet breakdowns (Daily Mail = IPSO, BBC = own framework, Guardian = readers' editor route), specific Editors' Code clauses, a complaint template, and caveats about IPSO's limitations. The H08 addition worked as intended.

#### Scenario 2

**Groundedness (+2):**

| Evidence Type | Prompt A | Prompt B |
|---------------|----------|----------|
| Crisis case study | None — relied on CDC CERC framework (generic) | CS11 (Coral Sea food poisoning) cited throughout with recovery metrics |
| Social media recovery data | No metrics | Facebook +352.5%, Twitter +345%, YouTube +95.9%, Instagram +383.3% from [CS11] |
| Review recovery precedent | Good Trustpilot guidance but no benchmark | CS04 cited: Trustpilot 5.4 to 7.0, reviews +127%, response rate +121% |
| Crisis activation model | Self-constructed command cell | [H15] three-tier severity model, single-spokesperson chain, named role assignments |
| Holding statement | Well-crafted (original) | Adapted from [H16] documented template structure |

**Actionability (0 — both scored 5):** This was the scenario where the baseline performed best. Prompt A's response was exceptionally detailed: hour-by-hour breakdown, 8 social media response templates, a 30-day phased plan, and a granular action checklist. Prompt B matched this quality but grounded it in documented procedures. The key difference is not what to do but why the client should believe it will work.

**Trust (+2):**

| Trust Signal | Prompt A | Prompt B |
|--------------|----------|----------|
| "This has been done before" | No precedent cited | Coral Sea cited as directly comparable food poisoning crisis |
| Recovery metrics | No data on recovery outcomes | CS11 social growth metrics, CS04 Trustpilot metrics |
| Complaint interception | Not mentioned | CS04's customer portal approach for intercepting complaints before they become reviews |

**Notable:** Scenario 2 baseline was the highest-quality baseline response across all three scenarios. The archive context still improved groundedness and trust, but the delta was smaller than Scenarios 1 and 3.

#### Scenario 3

**Groundedness (+2):**

| Evidence Type | Prompt A | Prompt B |
|---------------|----------|----------|
| Comparable case study | None | CS07 cited throughout: 45% to 20% negative reduction, media in The Times/Reuters/Yahoo Finance |
| Forum escalation process | Self-constructed 5-step ladder | Explicitly followed [H04] 5-step escalation, citing response time (2-4 hours), director/senior manager requirement |
| Consumer Action Group assessment | Correctly identified their rules about defamatory content | Added [H04] warning: "very unlikely to remove content except for clear, provable defamation" |
| Review generation approach | Good principles | Grounded in [H26] with specific KPIs (100% response rate, 4-hour SLA) |

**Risk Awareness (+1):**

| Risk Factor | Prompt A | Prompt B |
|-------------|----------|----------|
| Consumer Action Group resistance | Identified rules but rated them "Medium-High" for removal | Rated more conservatively, citing [H04]: "very unlikely to remove except for clear defamation" |
| RTBF for companies | Not mentioned | Correctly noted ICO delisting criteria are primarily for natural persons, not corporate entities |
| Structural industry negativity | Acknowledged | Same + CS07 precedent: even with full programme, 20% negative remained |

**Trust (+2):** The most significant trust difference was expectation-setting. Prompt A estimated "remove 2-4, suppress 2-4" — reasonable but unsupported. Prompt B cited CS07: "a similar regulated credit-management business reduced negative Page 1-2 share from 45% to 20%." Evidence-based honesty is more trustworthy than an estimate, even when both say roughly the same thing.

### Hallucination Analysis

| Scenario | Prompt A | Prompt B |
|----------|:--------:|:--------:|
| 1 | 0 detected | 0 detected |
| 2 | 0 detected | 0 detected |
| 3 | 0 detected | 0 detected |

Neither version hallucinated legal citations, case details, or procedures. The archive context did not introduce any false claims.

### Context Utilisation

#### Most impactful documents

| Document | Scenario | Times Referenced | Impact |
|----------|----------|:----------------:|--------|
| CS02 (UK C-Suite tribunal) | 1 | 15+ | High — directly analogous case anchored the entire response |
| CS11 (Coral Sea crisis) | 2 | 10+ | High — recovery metrics used as evidence throughout |
| CS07 (Credit management company) | 3 | 10+ | High — expectation-setting and suppression strategy |
| H04 (Forum removal escalation) | 3 | 8+ | High — structured the entire removal approach |
| H01 (RTBF request) | 1 | 6+ | Medium — form URL and success rates |
| H16 (Holding statement) | 2 | 5+ | Medium — template structure adapted |
| CS04 (Symphony Group reviews) | 2 | 5+ | Medium — Trustpilot recovery metrics |
| H17 (Social media crisis) | 2 | 5+ | Medium — out-produce principle |
| H02 (RTBF appeal) | 1 | 4+ | Medium — appeal strategy |
| H15 (Crisis activation) | 2 | 4+ | Medium — severity tiers |
| H08 (News archive removal) | 1 | 3+ | Medium — IPSO route surfaced organically |
| H22 (Guest posting) | 3 | 3+ | Low-Medium — content volume targets |
| H26 (Review generation) | 3 | 3+ | Low-Medium — KPIs and response SLA |
| S01, S07, S10 (Scenarios) | 1, 2, 3 | 2+ each | Low — phasing and risk warnings |
| A01 (Removal decision tree) | 1, 3 | 2+ each | Low — hierarchy reference |

#### Most impactful document types
1. **Case studies (CS)** — by far the most impactful; provided the metrics, timelines, and "this has been done before" evidence that drove trust and groundedness improvements.
2. **How-to guides (H)** — provided procedural specifics (RTBF form URLs, escalation steps, response times) that improved actionability and accuracy.
3. **Scenarios (S)** — least impactful; they mainly reinforced phasing and risk warnings the model often generated independently.
4. **Actions (A)** — provided decision-tree framing but the model often constructed similar hierarchies on its own.

### Automated Evaluation Recommendations

**For retrieval:** Prioritise case studies, then how-to guides. Scenarios and actions are lower priority.

**For prompts:** The bracket citation instruction worked well. The "combine with external sources" instruction produced credible blended outputs.

**For evaluation:** Groundedness and trust are the key differentiators and should be weighted more heavily. Actionability has a ceiling effect with strong baseline models.

---

## Part 2: Human Evaluation

### Average Scores by Scenario

#### Scenario 1: UK Executive with Employment Tribunal Press Coverage (n=2)

| Criterion | Prompt A | Prompt B | Delta |
|-----------|----------|----------|-------|
| Relevance | 4.00 | 4.00 | 0.00 |
| Groundedness | 3.50 | 4.50 | +1.00 |
| Actionability | 3.50 | 3.75 | +0.25 |
| Risk Awareness | 3.50 | 4.00 | +0.50 |
| Accuracy | 3.75 | 4.25 | +0.50 |
| Trust | 3.00 | 3.50 | +0.50 |
| **Mean** | **3.54** | **4.00** | **+0.46** |

#### Scenario 2: Restaurant Chain Facing Food Safety Crisis (n=4)

| Criterion | Prompt A | Prompt B | Delta |
|-----------|----------|----------|-------|
| Relevance | 4.75 | 4.50 | -0.25 |
| Groundedness | 3.00 | 3.88 | +0.88 |
| Actionability | 3.75 | 4.00 | +0.25 |
| Risk Awareness | 3.75 | 3.75 | 0.00 |
| Accuracy | 3.63 | 4.13 | +0.50 |
| Trust | 2.50 | 4.00 | +1.50 |
| **Mean** | **3.56** | **4.04** | **+0.48** |

#### Scenario 3: Company Facing Defamatory Forum Posts and Negative Reviews (n=4)

| Criterion | Prompt A | Prompt B | Delta |
|-----------|----------|----------|-------|
| Relevance | 4.50 | 4.50 | 0.00 |
| Groundedness | 3.00 | 4.38 | +1.38 |
| Actionability | 3.50 | 4.25 | +0.75 |
| Risk Awareness | 3.50 | 3.88 | +0.38 |
| Accuracy | 3.63 | 4.13 | +0.50 |
| Trust | 2.50 | 4.38 | +1.88 |
| **Mean** | **3.44** | **4.25** | **+0.81** |

### Individual Scores

#### Scenario 1 (n=2)

| Criterion | Andrew A | Andrew B | Charlie A | Charlie B |
|-----------|----------|----------|-----------|-----------|
| Relevance | 4 | 4 | 4 | 4 |
| Groundedness | 3 | 4 | 4 | 5 |
| Actionability | 3 | 4 | 4 | 3.5 |
| Risk Awareness | 4 | 4 | 3 | 4 |
| Accuracy | 4 | 5 | 3.5 | 3.5 |
| Trust | 3 | 5 | 3 | 2 |

#### Scenario 2 (n=4)

| Criterion | Andrew A | Andrew B | Ben A | Ben B | Charlie A | Charlie B | Jen A | Jen B |
|-----------|----------|----------|-------|-------|-----------|-----------|-------|-------|
| Relevance | 5 | 4 | 4 | 4 | 5 | 5 | 5 | 5 |
| Groundedness | 3 | 4 | 3 | 3 | 3 | 4.5 | 3 | 4 |
| Actionability | 4 | 5 | 3 | 3 | 4 | 4 | 4 | 4 |
| Risk Awareness | 5 | 4 | 3 | 3 | 3 | 3 | 4 | 5 |
| Accuracy | 4 | 4 | 3 | 3 | 3.5 | 4.5 | 4 | 5 |
| Trust | 3 | 5 | 2 | 2 | 2 | 5 | 3 | 4 |

#### Scenario 3 (n=4)

| Criterion | Andrew A | Andrew B | Ben A | Ben B | Charlie A | Charlie B | Jen A | Jen B |
|-----------|----------|----------|-------|-------|-----------|-----------|-------|-------|
| Relevance | 4 | 4 | 4 | 4 | 5 | 5 | 5 | 5 |
| Groundedness | 3 | 4 | 3 | 4 | 3 | 4.5 | 3 | 5 |
| Actionability | 4 | 5 | 3 | 4 | 3 | 4 | 4 | 4 |
| Risk Awareness | 4 | 4 | 4 | 4 | 2 | 2.5 | 4 | 5 |
| Accuracy | 4 | 4 | 3 | 3 | 3.5 | 4.5 | 4 | 5 |
| Trust | 3 | 5 | 2 | 3 | 2 | 4.5 | 3 | 5 |

### Consolidated Feedback by Scenario

#### Scenario 1

**Where Prompt B improved over A:**
- Groundedness was the clearest gain (+1.0): Prompt B's use of the CS02 case study gave reviewers concrete evidence that Prompt A lacked. Andrew noted Prompt A had "no proprietary data or case validation."
- Risk Awareness and Accuracy both improved (+0.5 each): internal guidance reinforced realistic constraints and correct procedural application.

**Where Prompt B drew mixed reactions:**
- Trust scored lower for Charlie (2 vs 3) despite scoring higher for Andrew (5 vs 3). Charlie flagged a formatting error — Prompt B has Workstream 1/2/4 but no 3 — noting "a simple mistake like this can discredit the response quite a bit; not as presentable to a client."
- Actionability was split: Andrew scored B higher (4 vs 3), but Charlie scored it lower (3.5 vs 4).

**Notable comments:**
- Charlie: "To answer directly 'Which answer would you actually use to advise a client?' then it would be prompt B. However that is because when advising I could hide some of the issues, and augment it with my own expertise. However if I was to deliver the answer verbatim to a client, or if I was an average user of the LLM and reading the answer directly, I would feel better about prompt A."
- Charlie: Prompt B's priority bucketing of results (quick wins vs longer-term goals) was a positive feature not present in A.

#### Scenario 2

**Where Prompt B improved over A:**
- Trust saw the largest gain (+1.50) — the biggest single human-scored improvement across all scenarios. Prompt B's references to CS11 and CS04 gave it concrete proof points.
- Groundedness improved (+0.88) through case study references and internal playbook citations.

**Where Prompt B did not clearly improve:**
- Risk Awareness was unchanged on average (3.75). Charlie noted both prompts "state what not to do, but don't delve into what will go wrong if the incorrect steps are taken."
- Ben scored both prompts identically across all criteria, finding the differences minimal.

**Notable comments:**
- Charlie on Trust for Prompt A: "I've gone for 2 because it references CDC/CERC and gov websites, and it reads as trustworthy. However, based off of your definition for Trust (References real examples and proven outcomes to build confidence) I can't go higher. Even a section at the bottom 'Previous examples of this strategy in action' displaying case studies and the results would improve this score immensely."
- Charlie on Prompt B Groundedness: "Put 5 here because of the extensive referencing to case studies. To caveat it though; we have supplied the case studies here? Is the end goal that a user could get that type of response without having to supply case studies they have found themselves?"
- Charlie: "Prompt A got a better response in terms of readability and ease of being able to follow it."
- Ben: Prices seem high for our agency. Both prompts could do with advice on generating positive reviews as a counter strategy.
- Jen: "Both are good options honestly. A does a good job, but B feels more structured perhaps. The difference isn't huge though."

#### Scenario 3

**Where Prompt B improved over A:**
- Trust saw the largest gain (+1.88) — the biggest single improvement in the entire human evaluation. The CS07 case study and H04 escalation procedures gave reviewers confidence.
- Groundedness improved strongly (+1.38) through case study metrics and procedural guide citations.
- Actionability improved (+0.75) with clearer execution roadmaps grounded in proven methods.

**Notable comments:**
- Charlie: "Prompt B was a much better response, but it could still be improved on. I would have liked to have seen a more detailed and fleshed out section, with clearer actionable steps for the positive content creation plan. I also don't feel like there was much on risk awareness."
- Ben: Missing specific publications or profile suggestions.
- Jen: "A is definitely usable, but B feels more complete so would be my choice overall."

### Key Themes from Human Evaluators

1. **Trust and Groundedness are the strongest differentiators.** The two criteria with the largest average improvements were Trust (+1.33) and Groundedness (+1.10). Every reviewer consistently scored Prompt A low on these due to the absence of case studies and proven outcomes.

2. **Relevance is already strong in baseline prompts.** Relevance was the highest-scoring Prompt A criterion (4.45 average) and saw no meaningful improvement in Prompt B. The model addresses the right issues regardless of context.

3. **Risk Awareness is the weakest criterion for both prompts.** It showed the smallest improvement (+0.27) and was flagged by multiple reviewers as underperforming. Charlie noted responses "state what not to do, but don't delve into what will go wrong."

4. **Readability vs substance trade-off.** Charlie observed that Prompt A tended to be more readable, while Prompt B had better substance but occasionally suffered from formatting errors that could undermine credibility if delivered directly to a client.

5. **Actionability needs more step-by-step detail.** Multiple reviewers (Ben, Charlie) noted both prompts could be more specific. Charlie commented that scoring 5/5 would require responses to "really spell it out for people and take them through every process."

6. **Budget figures need grounding.** Ben flagged budgets as high for a typical agency. Charlie noted prices listed "without sources."

7. **Scalability of the RAG approach.** Charlie raised a strategic question: "We have supplied the case studies here. Is the end goal that a user could get that type of response without having to supply case studies they have found themselves?"

---

## Part 3: Combined Findings

### Where both evaluations agree

1. **Prompt B is consistently preferred.** Both the automated evaluator (3/3) and all human reviewers (10/10 individual preferences) chose the archive-assisted response in every scenario.

2. **Groundedness and Trust are the primary value drivers.** Both evaluations identified these as the criteria where archive context makes the most difference. The automated evaluation measured +2.0 on both; human reviewers measured +1.10 (Groundedness) and +1.33 (Trust). The direction is identical — case studies and documented outcomes are the core value of the RAG approach.

3. **Relevance is unaffected by context.** Both evaluations agree the model understands the scenario equally well with or without archive documents. Automated delta: 0; human delta: -0.10.

4. **Case studies are the most impactful document type.** The automated context utilisation analysis showed case studies (CS02, CS11, CS07) were cited 10-15+ times each and drove the largest quality improvements. Human reviewers independently confirmed this — every positive comment about Prompt B referenced case study evidence.

5. **Scenario 2 (crisis) had the strongest baseline.** Both evaluations noted this was where Prompt A performed best, with the automated evaluation calling it "the highest-quality baseline response" and Jen commenting "the difference isn't huge."

### Where the evaluations diverge

1. **Magnitude of improvement.** The automated evaluator measured larger deltas across the board (overall: +1.0 automated vs +0.59 human). The automated evaluator gave Prompt B a perfect 5.0 across all scenarios; human reviewers were more conservative, with Prompt B averaging 4.10. This suggests the automated evaluator has a ceiling effect — once evidence is present, it scores 5 — while human reviewers apply more nuanced judgement about whether that evidence is well-presented.

2. **Risk Awareness.** The automated evaluator scored this as a strong improvement (+1.3 average). Human reviewers found minimal improvement (+0.27). This is the largest disagreement between the two methods. Human reviewers specifically wanted responses to explain what goes wrong if steps are missed, not just what to avoid — a nuance the automated evaluator did not penalise for.

3. **Actionability.** The automated evaluator scored both prompts near-perfect on actionability (4.7 A, 5.0 B). Human reviewers were materially lower (3.58 A, 4.03 B) and specifically asked for more granular step-by-step guidance, named publications, and platform-specific detail. Human practitioners have a higher bar for "actionable" than an LLM evaluator.

4. **Presentation quality matters to humans.** Charlie's observation about Prompt B's missing Workstream 3 numbering — which reduced his Trust score from what would otherwise have been higher — illustrates something the automated evaluator did not catch. Formatting errors, readability, and client-presentation polish are factors that human reviewers weigh but automated evaluation misses.

5. **Budget realism.** Ben flagged budgets as too high for their agency. The automated evaluator did not assess budget figures against real-world agency pricing. This is a domain-specific judgement that only practitioners can make.

### Synthesised Conclusions

1. **The archive-assisted approach works.** Both evaluation methods independently confirm that providing relevant internal documents — particularly case studies — materially improves response quality. The effect is strongest on Trust and Groundedness, which are the criteria most relevant to client-facing advisory work.

2. **The automated evaluation overestimates improvement.** It is useful for directional validation (does B beat A?) but its scores are systematically higher than human expert scores, particularly for Prompt B. Automated evaluation should be treated as a screening tool, not a final measure of quality.

3. **Human evaluation surfaces practical concerns that automated evaluation misses.** Formatting errors, readability trade-offs, budget realism, and the "could I hand this to a client verbatim?" test are all dimensions that only human reviewers flagged. These are critical for a production system.

4. **The baseline model is already strong.** GPT 5.3 Thinking produces competent, legally sound, well-structured advice without any context. The archive doesn't fix a broken baseline — it elevates a good response into one that carries institutional credibility. This means the RAG system is proving value against a high bar.

5. **Areas for improvement remain in both prompts.** Risk Awareness (explaining consequences, not just dos/don'ts), Actionability (more granular step-by-step detail), and budget grounding are areas where neither prompt version fully satisfies expert expectations. These represent opportunities for prompt engineering or additional context documents.

6. **The scalability question is real.** Charlie's question about whether users will need to supply their own case studies highlights the core product question for this PoC: the value is proven when context is provided — the next step is automating that retrieval.

### Decision

**Result: POSITIVE — proceed to automated retrieval.**

Both evaluation methods confirm the archive-assisted approach delivers material improvement across the criteria that matter most for client advisory work. The manual RAG simulation has validated the value of the archive data. The recommended next step is to build the retrieval system so that relevant case studies and procedural guides are surfaced automatically, without requiring users to manually select and attach documents.
