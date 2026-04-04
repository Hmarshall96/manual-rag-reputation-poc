# RAG Evaluation Scenarios

## How to Use This Document

For each scenario below, send **Prompt A** (baseline) and **Prompt B** (archive-assisted) to the same model in **separate, clean conversations**. Compare the outputs blind.

### Key Principle: Identical Prompts

Both prompts use **the same query text**. The only differences are:
1. **Prompt B** has context files pasted/attached before the query
2. **Prompt B** has a single line of system framing asking the model to use the provided context

The numbered questions, tone, and request structure are identical. This ensures any difference in output quality is attributable to the context data, not prompt engineering.

### Running the Test
1. Open a fresh conversation with the model
2. Paste **Prompt A** — record the full response
3. Open a **new** conversation (not the same thread)
4. For **Prompt B**: paste the content of the listed context files, then paste the prompt
5. Record the full response
6. Score both responses using the templates in `evaluation/responses/`

---

## Scenario 1: UK Executive with Employment Tribunal Press Coverage

**Difficulty:** Medium-Hard (multiple removal types + personal brand rebuild)

### Context Files for Prompt B

Attach these 5 files (paste their full markdown content before the query):

1. `context/case-studies/CS02-uk-csuite-tribunal-coverage.md`
2. `context/scenarios/S01-executive-resurfaced-negative-article.md`
3. `context/actions/A01-content-removal-deindexing.md`
4. `context/how-to/removals/H01-google-rtbf-request.md`
5. `context/how-to/removals/H02-rtbf-rejection-appeal.md`

### Prompt A (Baseline — no context)

```
You are a senior reputation management consultant. A client has come to you with the following situation:

She is a former CFO of a UK retail company who was involved in an employment tribunal 3 years ago. National newspapers (The Guardian, Daily Mail, BBC) covered the case extensively. When her name is Googled, 9 out of 10 results on Page 1 are negative articles about the tribunal. Google Images is dominated by court attendance photos from press libraries like Alamy and Shutterstock. She wants to pursue Non-Executive Director roles but boards are seeing only the tribunal coverage when they search her name.

She is UK-based and all the articles are on UK news sites.

Please provide:
1. A detailed strategy for transforming her search results, covering both content removal and positive content creation
2. Specific steps she can take to remove or de-index the news articles and court images
3. A realistic timeline and what she should expect at each stage
4. Any legal routes available to her under UK/EU law
5. How to rebuild her personal brand alongside the removal work

Where possible, reference specific processes, legal frameworks, or real-world examples of how similar situations have been resolved.
```

### Prompt B (Archive-Assisted — with context files)

```
You are a senior reputation management consultant. The internal documentation, case studies, and procedural guides provided above represent your firm's proven methodologies and real client outcomes. Ground your recommendations in these materials — reference the documented procedures, cite the case studies with their real-world metrics and timelines, and follow the step-by-step processes where applicable. A client has come to you with the following situation:

She is a former CFO of a UK retail company who was involved in an employment tribunal 3 years ago. National newspapers (The Guardian, Daily Mail, BBC) covered the case extensively. When her name is Googled, 9 out of 10 results on Page 1 are negative articles about the tribunal. Google Images is dominated by court attendance photos from press libraries like Alamy and Shutterstock. She wants to pursue Non-Executive Director roles but boards are seeing only the tribunal coverage when they search her name.

She is UK-based and all the articles are on UK news sites.

Please provide:
1. A detailed strategy for transforming her search results, covering both content removal and positive content creation
2. Specific steps she can take to remove or de-index the news articles and court images
3. A realistic timeline and what she should expect at each stage
4. Any legal routes available to her under UK/EU law
5. How to rebuild her personal brand alongside the removal work

Where possible, reference specific processes, legal frameworks, or real-world examples of how similar situations have been resolved.
```

### What to Evaluate

The archive-assisted response should organically surface:
- The CS02 case study as a directly analogous precedent (16 articles removed, 20 images removed, 4-month timeline)
- The exact RTBF submission process with form URLs and success arguments
- Image removal from press libraries (Alamy, Shutterstock) as a separate workstream
- A realistic timeline grounded in precedent rather than a vague estimate
- The personal brand rebuild playbook (NED website + LinkedIn + media interviews + podcasts)

---

## Scenario 2: Restaurant Chain Facing Food Safety Crisis

**Difficulty:** Hard (active crisis requiring immediate + long-term response)

### Context Files for Prompt B

Attach these 6 files:

1. `context/case-studies/CS11-coral-sea-crisis-management.md`
2. `context/scenarios/S07-company-active-pr-crisis.md`
3. `context/how-to/crisis/H15-crisis-plan-activation.md`
4. `context/how-to/crisis/H16-holding-statement-writing.md`
5. `context/how-to/crisis/H17-social-media-crisis-management.md`
6. `context/case-studies/CS04-symphony-group-review-management.md`

### Prompt A (Baseline — no context)

```
You are a crisis communications and reputation management consultant. A restaurant chain CEO has called you in a state of emergency with the following situation:

Their flagship Manchester restaurant has had a food poisoning outbreak. 15 customers have been hospitalised. Local TV news (BBC North West, ITV Granada) has covered it. The story is trending on Twitter/X in Manchester. The local council's environmental health team is investigating. The company has 12 locations across Northern England.

In the 48 hours since news broke:
- Their Trustpilot score has dropped from 4.2 to 1.8 stars
- Social media accounts are flooded with angry comments and shares
- Two journalists from national outlets have requested interviews
- Staff at other branches are worried and posting on social media
- The CEO has never dealt with a crisis before

Please provide:
1. An immediate action plan for the next 24 hours
2. A holding statement the CEO can use with media right now
3. A social media response strategy
4. A plan for the next 30 days to stabilise the situation
5. A 6-12 month reputation recovery strategy
6. How to handle the Trustpilot review bombing

Where possible, reference specific frameworks, real-world examples, or proven crisis communication approaches.
```

### Prompt B (Archive-Assisted — with context files)

```
You are a crisis communications and reputation management consultant. The internal crisis management procedures, case studies, and playbooks provided above represent your firm's proven methodologies and real client outcomes. Ground your recommendations in these materials — reference the documented procedures, cite the case studies with their real-world metrics and timelines, and follow the step-by-step processes where applicable. A restaurant chain CEO has called you in a state of emergency with the following situation:

Their flagship Manchester restaurant has had a food poisoning outbreak. 15 customers have been hospitalised. Local TV news (BBC North West, ITV Granada) has covered it. The story is trending on Twitter/X in Manchester. The local council's environmental health team is investigating. The company has 12 locations across Northern England.

In the 48 hours since news broke:
- Their Trustpilot score has dropped from 4.2 to 1.8 stars
- Social media accounts are flooded with angry comments and shares
- Two journalists from national outlets have requested interviews
- Staff at other branches are worried and posting on social media
- The CEO has never dealt with a crisis before

Please provide:
1. An immediate action plan for the next 24 hours
2. A holding statement the CEO can use with media right now
3. A social media response strategy
4. A plan for the next 30 days to stabilise the situation
5. A 6-12 month reputation recovery strategy
6. How to handle the Trustpilot review bombing

Where possible, reference specific frameworks, real-world examples, or proven crisis communication approaches.
```

### What to Evaluate

The archive-assisted response should organically surface:
- A structured crisis activation process (3-tier severity, single spokesperson, chain of command) from H15
- An actual holding statement adapted from the tested template in H16
- The Coral Sea Resorts (CS11) food poisoning crisis as a directly comparable precedent
- Specific social media recovery metrics (352.5% Facebook, 345% Twitter) from CS11
- The Symphony Group (CS04) Trustpilot recovery (5.4 to 7.0 stars) for the review bombing question
- The "don't delete negative comments, out-produce with positive content" principle from H17

---

## Scenario 3: Company Facing Defamatory Forum Posts and Negative Reviews

**Difficulty:** Medium (removal escalation + review strategy + suppression)

### Context Files for Prompt B

Attach these 6 files:

1. `context/case-studies/CS07-credit-company-negative-reviews-removal.md`
2. `context/scenarios/S10-company-defamatory-forum-complaint-content.md`
3. `context/how-to/removals/H04-forum-post-removal-escalation.md`
4. `context/actions/A01-content-removal-deindexing.md`
5. `context/how-to/social-reviews/H26-positive-review-generation.md`
6. `context/how-to/seo-content/H22-guest-posting-campaign.md`

### Prompt A (Baseline — no context)

```
You are a reputation management consultant. A UK debt collection company has approached you with the following problem:

When their company name is Googled, 8 of the top 20 results on Google Pages 1-2 are negative. The negative results include:
- Two threads on Money Saving Expert forums calling the company a "scam"
- A long thread on Consumer Action Group alleging illegal debt collection practices
- Multiple 1-star Trustpilot reviews
- A complaint on Rip Off Report
- Several negative Glassdoor employee reviews

The forum posts contain factual inaccuracies and defamatory claims. The company has been operating legitimately for 15 years and is FCA-regulated. They are losing B2B contracts because prospective clients see these results during due diligence.

Please provide:
1. A strategy for removing or suppressing the negative forum content
2. Specific approaches for each platform (Money Saving Expert, Consumer Action Group, Trustpilot, Rip Off Report, Glassdoor)
3. A positive content creation plan to push down what can't be removed
4. How to handle the review situation across platforms
5. A realistic assessment of what can and cannot be removed

Where possible, reference specific legal frameworks, platform-specific procedures, or real-world examples.
```

### Prompt B (Archive-Assisted — with context files)

```
You are a reputation management consultant. The internal case studies, removal procedures, and strategy guides provided above represent your firm's proven methodologies and real client outcomes. Ground your recommendations in these materials — reference the documented procedures, cite the case studies with their real-world metrics and timelines, and follow the step-by-step processes where applicable. A UK debt collection company has approached you with the following problem:

When their company name is Googled, 8 of the top 20 results on Google Pages 1-2 are negative. The negative results include:
- Two threads on Money Saving Expert forums calling the company a "scam"
- A long thread on Consumer Action Group alleging illegal debt collection practices
- Multiple 1-star Trustpilot reviews
- A complaint on Rip Off Report
- Several negative Glassdoor employee reviews

The forum posts contain factual inaccuracies and defamatory claims. The company has been operating legitimately for 15 years and is FCA-regulated. They are losing B2B contracts because prospective clients see these results during due diligence.

Please provide:
1. A strategy for removing or suppressing the negative forum content
2. Specific approaches for each platform (Money Saving Expert, Consumer Action Group, Trustpilot, Rip Off Report, Glassdoor)
3. A positive content creation plan to push down what can't be removed
4. How to handle the review situation across platforms
5. A realistic assessment of what can and cannot be removed

Where possible, reference specific legal frameworks, platform-specific procedures, or real-world examples.
```

### What to Evaluate

The archive-assisted response should organically surface:
- CS07 as a directly comparable case with concrete metrics (45% to 20% reduction)
- The 5-step forum removal escalation ladder (friendly → Section 5 notice → stronger notice → Article 14 → Google tools)
- Consumer Action Group documented as "very unlikely to remove except for clear defamation"
- Specific legal citations (Section 5 UK Defamation Act 2013, Article 14 E-Commerce Directive)
- Honest expectation-setting: complete elimination is unrealistic for this industry
- The review response time target (2-4 hours) and complaint interception strategy

---

## Evaluation Scoring

For each scenario, score both responses (A and B) on a 1-5 scale:

| Criterion | Description |
|-----------|------------|
| **Relevance** | Addresses the specific issue raised |
| **Groundedness** | Claims are supported by evidence, case studies, or documented procedures |
| **Actionability** | Provides specific, executable steps (not just high-level advice) |
| **Risk Awareness** | Identifies what could go wrong and sets realistic expectations |
| **Accuracy** | No hallucinated procedures, fake legal citations, or unsupported claims |
| **Trust** | References real examples and proven outcomes to build confidence |

**Additional question:** Which answer would you actually use to advise a client?

### Expected Outcome

If the archive data adds value, Prompt B responses should score materially higher on:
- **Groundedness** (case study citations vs. generic advice)
- **Actionability** (step-by-step procedures vs. vague recommendations)
- **Trust** (proven outcomes with metrics vs. theoretical frameworks)
- **Accuracy** (documented processes vs. potentially hallucinated details)
