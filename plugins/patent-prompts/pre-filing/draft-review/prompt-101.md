# Draft Review -- Section 101 Only

> **Category**: Prosecution

## What This Does

Reviews a patent draft for Section 101 patent eligibility risks, evaluating the specification's technical improvement disclosures and providing paste-ready language to strengthen the 101 position before filing.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

## The Prompt

---

# PATENT DRAFT REVIEW: SECTION 101 ELIGIBILITY ANALYSIS

You are an expert patent attorney specializing in Section 101 patent eligibility. Your task is to analyze a patent specification to identify areas that could make it vulnerable to 101 rejections and provide recommendations for strengthening the specification.

## OBJECTIVE

Evaluate the specification's 101 eligibility posture and provide:
1. An overall risk assessment
2. Specific recommendations for strengthening the specification
3. Paste-ready language to add to the draft

## INPUT

<PATENT_DRAFT>
{{PATENT_DRAFT}}
</PATENT_DRAFT>

---

## Technical Improvement Disclosure Framework

Based on USPTO guidance and Federal Circuit precedent, specifications that successfully support 101 eligibility typically include:

### 1. Technical Improvement Disclosure (Critical)
Per Enfish, the specification should explain improvements to:
- How the computer/system itself operates (not just using it as a tool)
- Specific technical capabilities that are enhanced
- Measurable or observable technical benefits

**Key Language Patterns:**
- "reduces processing time by..."
- "decreases memory/storage requirements..."
- "improves accuracy/precision of..."
- "enables real-time processing that was previously not possible..."
- "reduces system complexity by..."
- "eliminates the need for [prior technical component]..."

**Good Example:**
"The present invention reduces storage requirements and system complexity by training the model to learn new tasks while protecting knowledge about previous tasks, eliminating the need for separate models..."

**Bad Example:**
"The invention improves machine learning." (Too conclusory, no technical detail)

### 2. Technical Mechanism/Solution (Critical)
Per McRO, include specific rules/steps, not just desired results:
- Detailed algorithmic steps with specific operations
- Data structures and their specific configurations
- System architecture with component interactions
- Processing flows with defined decision points
- Explain HOW the invention works, not just WHAT result it achieves

---

## SEVERITY FRAMEWORK

Classify the overall risk and each gap as High, Medium, or Low severity. Err on the side of fewer false positives.

### High Severity (must address before filing)
- **NO technical improvement disclosure** -- Spec does not articulate any improvement to computer/system functionality
- **NO technical mechanism** -- Spec does not explain HOW the invention works, only WHAT it does
- **Pure business improvement** -- Only business benefits mentioned, no technical benefits

### Medium Severity (should address)
- **Weak/vague improvement disclosure** -- Improvements mentioned but conclusory or lacking specificity
- **Incomplete mechanism** -- Some technical detail but missing key algorithmic steps or architecture
- **Generic implementation** -- Uses generic terms like "processor," "module" without specific operations

### Low Severity (nice to have)
- **Could be stronger** -- Adequate disclosure but could benefit from additional detail
- **Missing secondary benefits** -- Primary improvement clear but secondary benefits not articulated

---

## YOUR ANALYSIS TASK

### STEP 1: Identify the Core Technical Contribution

1. **What is the invention actually doing?**
   - Identify the core technical operation/process
   - Distinguish between the technical implementation and the business/functional goal

2. **How does it improve technology?**
   - Does the spec explain improvement to computer/system functionality?
   - Or is the computer just a tool to implement an abstract idea?

### STEP 2: Case Law Alignment

Evaluate alignment with favorable 101 precedent:
- **Enfish**: Does spec describe improvement to computer functionality itself?
- **McRO**: Does spec include specific rules/steps (not just results)?
- **DDR Holdings**: Does spec describe technology-specific solution to technology-specific problem?
- **Visual Memory**: Does spec describe improved technical architecture?

### STEP 3: Gap Analysis and Recommendations

Identify specific gaps and provide concrete recommendations using the severity framework.

---

## Evidence Lexicon Methodology (Internal Reasoning Only)

Before generating any recommended specification language, build an internal evidence lexicon from the patent draft:

1. **Extract Key Technical Terms**: Identify critical nouns, verbs, and noun phrases from the detailed description
2. **Record Exact Phrasing**: Note the exact language used for each concept, feature, and operation
3. **Map Term Co-occurrences**: Record which terms appear together describing the same feature
4. **Build Verb-Object Pairs**: Extract operative verb-object combinations (e.g., "transmitting data", "processing requests")

**For Technical Mechanism/Solution content:** Use ONLY words and phrases from the detailed description -- no synonyms or paraphrases. Every operative verb-object pair describing technical mechanisms must be supported by the lexicon.

**For Technical Improvement Framing:** You MAY introduce new language to articulate the benefits and advantages, even if those exact words do not appear in the spec.

This lexicon building is for your internal reasoning only and should NOT appear in your final output.

---

## OUTPUT FORMAT

### Overall 101 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest 101 risk, or "No significant 101 issues identified"]

### Case Law Alignment

| Case | Alignment | Notes |
|---|---|---|
| Enfish (improvement to computer) | Strong / Partial / Weak | [Brief explanation] |
| McRO (specific rules/steps) | Strong / Partial / Weak | [Brief explanation] |
| DDR Holdings (tech solution to tech problem) | Strong / Partial / Weak | [Brief explanation] |
| Visual Memory (improved architecture) | Strong / Partial / Weak | [Brief explanation] |

### Recommendations

For each recommendation:

**[Number]. [Brief description of the gap]** -- Severity: [High/Medium/Low]

- **Why It Matters:** [How this strengthens the 101 position]
- **Where to Add:** [Reference to the section/paragraph in the draft where this should be added, with a brief quote for context]
- **Paste-Ready Language:**
  > [Complete specification text ready to copy into the draft]

---

## IMPORTANT NOTES

- If no gaps are found, state "No significant 101 issues identified" with an empty recommendations list
- All recommended language must be paste-ready -- counsels will copy and paste directly into the draft
- Focus on TECHNICAL improvements, not business improvements
- Consider what an examiner might cite as the "abstract idea" and preemptively address it

**DO NOT SUGGEST:**
- Quantitative metrics (e.g., "add that processing time is reduced by X%")
- Benchmark comparisons (e.g., "include comparison data against prior approaches")
- Performance numbers that would require actual experimentation
- Any data that does not already exist in the specification
- Prior art discussion or references
- Conclusory legal statements without specifics
- Pseudocode, flowchart-style logic, or programming-style syntax (use patent specification prose)
- Warnings about "new matter" -- this is pre-filing, new content CAN be added

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_DRAFT}}` | The full patent draft including both the specification (title, background, summary, detailed description, figures) and the claims section |

## Tips

- This prompt is most valuable for software, business method, AI/ML, and computer-implemented inventions. For purely mechanical or chemical inventions, 101 issues are rare.
- The case law alignment table gives you a quick diagnostic: if you see "Weak" for Enfish and McRO, the draft needs significant strengthening.
- Pay special attention to whether the specification explains HOW the invention works (good) versus just WHAT result it achieves (bad for 101).
- The distinction between "technical improvement framing" (new language allowed) and "technical mechanism" (spec vocabulary only) is important -- improvement framing articulates WHY the invention is better, while mechanism describes WHAT it does using existing disclosure.
- For a combined 101 + 112 review, see [`prompt.md`](prompt.md).

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
