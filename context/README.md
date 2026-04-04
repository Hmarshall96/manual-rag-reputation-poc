# Reputation Management Context Files

This folder contains structured markdown files designed to be injected into LLM prompts as context for online reputation management queries. The files are optimized for vector store retrieval — each is a small, focused chunk (500-1500 words) with a clear semantic focus.

## Structure

```
context/
├── scenarios/        14 files — "What situation am I dealing with?"
├── actions/          10 files — "What strategy should I follow?"
├── how-to/           28 files — "How do I execute this step-by-step?"
│   ├── removals/     14 guides (RTBF, takedowns, platform-specific)
│   ├── crisis/        3 guides (crisis plan, holding statements, social)
│   ├── seo-content/   6 guides (article SEO, schema, guest posting)
│   ├── social-reviews/ 4 guides (audit, profiles, reviews, monitoring)
│   └── process/       1 guide  (client assessment)
├── case-studies/     11 files — Real examples with outcomes and lessons
├── README.md         This file
└── CONTRIBUTING.md   How to add/update content
```

## How to Use

### For Vector Store Retrieval
Each file has YAML frontmatter with `id`, `title`, `type`, and cross-reference fields. Embed all files and retrieve by semantic similarity to the user's query.

### For Manual Context Injection
1. Identify the **scenario** that matches the user's situation (S01-S14)
2. The scenario file references relevant **actions** (A01-A10) and **how-to guides** (H01-H28)
3. Include the scenario + 1-2 most relevant action files + the specific how-to guide for the immediate need
4. Add a **case study** (CS01-CS11) if a real-world example would help ground the response

### Cross-Reference System
- **S** = Scenario (entry point)
- **A** = Action (strategic approach)
- **H** = How-To (step-by-step procedure)
- **CS** = Case Study (real-world example)

## File Inventory

### Scenarios (S01-S14)
| ID | Title | Severity |
|----|-------|----------|
| S01 | Executive facing resurfaced negative article | High |
| S02 | Individual with criminal record in search results | High |
| S03 | Professional targeted by defamatory forum posts | Medium-High |
| S04 | Unwanted personal images/content indexed by Google | Medium |
| S05 | Person seeking Right to Be Forgotten de-listing | Medium |
| S06 | Company hit by wave of negative reviews | Medium-High |
| S07 | Company facing active PR crisis | Critical |
| S08 | Negative results dominating brand SERP | High |
| S09 | Post-crisis reputation rebuild | Medium |
| S10 | Company facing defamatory forum/complaint site content | Medium-High |
| S11 | New client onboarding and assessment | Low |
| S12 | Proactive reputation building (weak presence) | Low |
| S13 | Reputation audit and monitoring setup | Low |
| S14 | Wikipedia page management | Medium |

### Actions (A01-A10)
| ID | Title |
|----|-------|
| A01 | Content Removal & De-indexing |
| A02 | Positive Content Creation & SEO Suppression |
| A03 | Crisis Communications Response |
| A04 | Review Management & Response |
| A05 | Social Media Profile Optimization |
| A06 | Reputation Audit & Monitoring |
| A07 | Legal & Regulatory Escalation |
| A08 | Thought Leadership & PR Placement |
| A09 | Technical SEO & Web Property Optimization |
| A10 | Client Onboarding & Goal Setting |

### How-To Guides (H01-H28)
| ID | Title | Category |
|----|-------|----------|
| H01 | Google RTBF Request | Removals |
| H02 | RTBF Rejection Appeal | Removals |
| H03 | Defamation Takedown Letter | Removals |
| H04 | Forum Post Removal Escalation | Removals |
| H05 | DMCA Copyright Removal | Removals |
| H06 | Google Review Removal | Removals |
| H07 | Facebook Content Removal | Removals |
| H08 | News Archive Removal | Removals |
| H09 | Google Legal De-indexing | Removals |
| H10 | Amazon Content Removal | Removals |
| H11 | LinkedIn Defamatory Content | Removals |
| H12 | Criminal Record Search Deletion | Removals |
| H13 | Google Autocomplete Removal | Removals |
| H14 | US-Specific Removals | Removals |
| H15 | Crisis Plan Activation | Crisis |
| H16 | Holding Statement Writing | Crisis |
| H17 | Social Media Crisis Management | Crisis |
| H18 | Article Reputation SEO | SEO/Content |
| H19 | Schema Markup for Reputation | SEO/Content |
| H20 | Featured Snippets Optimization | SEO/Content |
| H21 | WordPress Client Site Setup | SEO/Content |
| H22 | Guest Posting Campaign | SEO/Content |
| H23 | Backlink Building for Suppression | SEO/Content |
| H24 | Social Media Audit & Setup | Social/Reviews |
| H25 | Profile Optimization | Social/Reviews |
| H26 | Positive Review Generation | Social/Reviews |
| H27 | Reputation Monitoring Setup | Social/Reviews |
| H28 | Client Reputation Assessment | Process |

### Case Studies (CS01-CS11)
| ID | Title | Client Type |
|----|-------|-------------|
| CS01 | CCI Global - International Telecoms Negative Press | Company |
| CS02 | UK C-Suite Executive - Employment Tribunal Coverage | Individual |
| CS03 | US Tech CEO - Toxic Reputation to Thought Leader | Individual |
| CS04 | The Symphony Group - Review Management | Company |
| CS05 | UK Technology Company - Rebranding | Company |
| CS06 | Paysafe - Global Multi-Brand Reputation Audit | Company |
| CS07 | UK Credit Management - Negative Reviews/Removal | Company |
| CS08 | UK Accountancy Firm - Authority Building | Company |
| CS09 | Global Nuclear Fuel - Stakeholder Reputation Review | Company |
| CS10 | Niche European Hotel - PR and Visibility Recovery | Company |
| CS11 | Coral Sea Resorts - Crisis Management and Recovery | Company |
