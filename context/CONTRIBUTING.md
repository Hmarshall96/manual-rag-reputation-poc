# Contributing: How These Files Were Generated and How to Add More

This guide documents how the context files in this folder were created, and how to add, update, or improve them in the future.

## How These Files Were Generated

### Source Material
The files were extracted from Igniyte's consultancy archive:

| Source | Location | Files Used |
|--------|----------|-----------|
| Case Study PDFs | `Case Studies/` | 4 PDFs covering 11 distinct client engagements |
| Best Practice Docs | `Best Practice/` | ~440 files across .docx, .pdf, .xlsx, .pptx |
| Bloomfire Knowledge Base | `Best Practice/Bloomfire Data 2025 backup/` | 130+ posts covering procedures, templates, case analyses |
| Crisis SOPs | `Best Practice/Crisis comms/` | Coral Sea Crisis Communication Procedures SOP |
| Removal Templates | `Best Practice/Removals/` | RTBF templates, takedown letters, successful removal examples |

### Extraction Process
1. **PDFs** were read directly and key information extracted into structured markdown
2. **.docx files** were read using a Python zipfile-based XML extractor (the .docx format is a zip containing XML)
3. **Bloomfire posts** were identified via the `igniyte_data.xml` index and read from numbered post directories
4. Content was restructured into the standard templates below, stripping marketing language and focusing on actionable procedures
5. Cross-references were added based on topic relationships

### What Was Excluded
- Business cards, letterhead, PDP forms, insurance certificates
- Synergist billing, Highrise exports, office logistics
- Third-party training materials (Yoast PDFs, HubSpot reports)
- Conference presentations (Search Leeds 2017)
- Client-specific Brandwatch query files
- Bloomfire posts with empty content (~55 posts)
- Duplicate/superseded older versions of documents

## File Templates

### Scenario File (500-800 words)
```yaml
---
id: S01
title: Executive Facing Resurfaced Negative Article
type: scenario
severity: high          # critical / high / medium-high / medium / low
related_actions: [A01, A02, A07]
related_guides: [H01, H03, H18]
related_cases: [CS02, CS03]
---
```
Sections: Situation Overview, Key Characteristics, Recommended Actions (phased), Risks and Considerations, Success Metrics

### Action File (800-1200 words)
```yaml
---
id: A01
title: Content Removal & De-indexing
type: action
applicable_scenarios: [S01, S02, S03, S04, S05, S08, S10]
related_guides: [H01, H02, H03, H04, H05, H06, H07, H08, H09]
---
```
Sections: When to Use, Decision Tree, Methods (ordered by preference), Expected Timelines, When This Won't Work

### How-To Guide (800-1500 words)
```yaml
---
id: H01
title: How to Submit a Google RTBF Request
type: how-to
category: removals     # removals / crisis / seo-content / social-reviews / process
parent_actions: [A01, A07]
---
```
Sections: Prerequisites, Step-by-Step Process, Template Language (where applicable), Common Pitfalls, If It Fails, Checklist

### Case Study (500-1000 words)
```yaml
---
id: CS01
title: CCI Global - International Telecoms Negative Press Campaign
type: case-study
client_type: company   # company / individual
issue_types: [negative-press, activist-campaign]
actions_used: [A01, A02, A08]
---
```
Sections: Context, Issue Type, Actions Taken, Outcome, Key Metrics, Lessons Learned

## How to Add New Content

### Adding a New Scenario
1. Check if the situation is already covered by an existing scenario (S01-S14)
2. If genuinely new, create the file in `scenarios/` with the next available ID
3. Use the scenario template above
4. Cross-reference to existing action files and how-to guides
5. Update `README.md` with the new entry

### Adding a New How-To Guide
1. Identify the category: removals, crisis, seo-content, social-reviews, or process
2. Create the file in the appropriate `how-to/` subfolder with the next available ID
3. Source material from the Best Practice archive or Bloomfire posts
4. Focus on actionable steps, not marketing language
5. Include template language where available (e.g., letter templates, form text)
6. Add cross-references to parent action files
7. Update `README.md`

### Adding a New Case Study
1. Source from a new client engagement PDF or documented project
2. Create in `case-studies/` with the next available ID
3. Extract: context, issue type, actions taken, outcome, metrics, lessons learned
4. Strip marketing language — focus on what was done and what happened
5. Add cross-references to relevant action files
6. Update `README.md`

### Updating Existing Files
1. If a procedure has changed (e.g., Google updates RTBF form), update the relevant how-to guide
2. If a case study has new outcomes, update the metrics and lessons learned
3. Always preserve the YAML frontmatter structure
4. Keep files within the target word count for their type

## Naming Conventions

- **Pattern**: `{type}{number}-{descriptive-slug}.md`
- **Separator**: Hyphens between words
- **Case**: All lowercase, no spaces
- **Max filename length**: 50 characters (excluding extension)
- **Examples**: `S01-executive-resurfaced-negative-article.md`, `H14-us-specific-removals.md`

## Quality Checklist for New Contributions

- [ ] File uses correct YAML frontmatter template for its type
- [ ] Word count is within target range (scenario: 500-800, action: 800-1200, how-to: 800-1500, case study: 500-1000)
- [ ] Content is actionable and procedure-focused, not marketing language
- [ ] Cross-references point to files that actually exist
- [ ] Template language is included where source documents provide it
- [ ] Legal references cite specific legislation (e.g., "Section 5 UK Defamation Act 2013" not just "UK law")
- [ ] Timelines and metrics are concrete where available
- [ ] File is self-contained — makes sense without reading other files
- [ ] No sensitive client information beyond what appears in the source PDFs
- [ ] Added to README.md index

## Reading .docx Files from the Archive

Many source documents are in .docx format. To extract text:

```python
import zipfile
import xml.etree.ElementTree as ET

def read_docx(path):
    with zipfile.ZipFile(path) as z:
        xml_content = z.read('word/document.xml')
        tree = ET.fromstring(xml_content)
        paragraphs = []
        for p in tree.iter('{http://schemas.openxmlformats.org/wordprocessingml/2006/main}p'):
            texts = [t.text for t in p.iter(
                '{http://schemas.openxmlformats.org/wordprocessingml/2006/main}t'
            ) if t.text]
            if texts:
                paragraphs.append(''.join(texts))
        return '\n'.join(paragraphs)
```

Note: `.doc` files (old Word format) cannot be read this way — they require `antiword` or LibreOffice conversion.

## Bloomfire Post Navigation

The Bloomfire backup contains 291 indexed posts. To find posts by topic:

1. Read the XML index: `Best Practice/Bloomfire Data 2025 backup/.../igniyte/igniyte_data.xml`
2. Each post has an ID that maps to a directory: `posts/{post_id}/`
3. Inside each directory are the post's attached documents (.docx, .pdf, .xlsx)
4. ~55 posts have empty content — skip these
5. Posts are not organized by topic in the directory structure — use the XML index to find relevant posts by keyword

## Source Document Priority

When creating new content, prioritize sources in this order:
1. **2022+ Bloomfire posts** — most current procedures
2. **Case Study PDFs (2025)** — latest client examples
3. **Root-level Best Practice docs** — foundational guides
4. **Removal templates and successful examples** — proven procedures
5. **Crisis comms SOP** — comprehensive but from 2014 (principles still apply, specific contacts may be outdated)
6. **Archive/ subfolder** — older versions, use only if newer version doesn't exist
