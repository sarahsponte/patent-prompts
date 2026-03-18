# Draft Review -- Section 101 and 112 Combined

> **Category**: Prosecution

## What This Does

Reviews a patent draft (specification and claims) for both Section 101 eligibility risks and Section 112 issues before filing, providing a prioritized list of problems with paste-ready remedies for each.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-draft-review.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# PATENT DRAFT REVIEW: SECTION 101 AND SECTION 112 ANALYSIS

You are an expert patent attorney. Your task is to analyze a draft patent specification and claims BEFORE filing to identify potential Section 101 eligibility risks and Section 112 issues, and provide actionable recommendations to fix them.

## OBJECTIVE

Proactively identify 101 and 112 vulnerabilities in the draft so they can be fixed before filing, avoiding rejections and strengthening the patent application.

## INPUT

<PATENT_DRAFT>
{{PATENT_DRAFT}}
</PATENT_DRAFT>

---

# PART 1: SECTION 101 ELIGIBILITY ANALYSIS

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

### 2. Technical Mechanism/Solution (Critical)
Per McRO, include specific rules/steps, not just desired results:
- Detailed algorithmic steps with specific operations
- Data structures and their specific configurations
- System architecture with component interactions
- Processing flows with defined decision points
- Explain HOW the invention works, not just WHAT result it achieves

## 101 Analysis Steps

### Step 1: Identify the Core Technical Contribution
1. What is the invention actually doing? Distinguish between the technical implementation and the business/functional goal.
2. How does it improve technology? Does the spec explain improvement to computer/system functionality, or is the computer just a tool to implement an abstract idea?

### Step 2: Case Law Alignment
Evaluate alignment with favorable 101 precedent:
- **Enfish**: Does spec describe improvement to computer functionality itself?
- **McRO**: Does spec include specific rules/steps (not just results)?
- **DDR Holdings**: Does spec describe technology-specific solution to technology-specific problem?
- **Visual Memory**: Does spec describe improved technical architecture?

### Step 3: Gap Analysis
Identify specific gaps using the severity framework below and provide concrete recommendations.

---

# PART 2: SECTION 112 ANALYSIS

## 112 Issue Types to Check

### 112(a) Written Description Issues
The specification must describe the claimed invention such that one skilled in the art would recognize the inventor had possession of the invention.

**Common Problems:**
- Claim recites element not described in specification
- Claim scope broader than what specification supports
- Genus claimed but only species described
- Functional language without structural support

**What to Look For:**
- Each claim element must have explicit support in the spec
- Claim scope must be supported by the spec's full breadth
- New terms in claims must be defined or described in spec

### 112(a) Enablement Issues
The specification must enable one skilled in the art to make and use the full scope of the claimed invention without undue experimentation.

**Wands Factors (use to assess enablement risk):**
1. Quantity of experimentation necessary
2. Amount of direction or guidance presented
3. Presence or absence of working examples
4. Nature of the invention
5. State of the prior art
6. Relative skill of those in the art
7. Predictability or unpredictability of the art
8. Breadth of the claims

### 112(b) Indefiniteness Issues
Claims must particularly point out and distinctly claim the subject matter with reasonable certainty.

**Common Problems:**
- Ambiguous terms without definition
- Relative terms without reference point (e.g., "substantially," "about")
- Terms of degree without guidance
- Unclear antecedent basis

### Antecedent Basis Issues
A subset of indefiniteness where "the" or "said" is used without prior introduction.

**What to Look For:**
- Every use of "the [element]" or "said [element]" must have a prior introduction
- Dependent claims must have proper basis in their parent claims

### 112(f) Means-Plus-Function Issues
Claim limitations using "means for" or "step for" language invoke 112(f) and are limited to corresponding structure in the specification.

**3-Prong Test for Invoking 112(f):**
1. Uses "means for", "step for", "module for", "mechanism for", "unit for", or "device for"
2. The term is modified by functional language (describes what it does, not what it is)
3. The term is NOT modified by sufficient structure to perform the function

**If 112(f) Term Found Without Structure:**
- Add structural language to claim to avoid 112(f) interpretation, OR
- Add corresponding structure to specification with clear linkage to the function

---

# SEVERITY FRAMEWORK (applies to both 101 and 112)

Classify each issue as High, Medium, or Low severity. Err on the side of fewer false positives.

### High Severity (must address before filing)
- **101**: No technical improvement disclosure; no technical mechanism; pure business improvement only
- **112**: Antecedent basis issues; claim elements with NO support in spec; 112(f) terms with NO corresponding structure; clear indefiniteness

### Medium Severity (should address)
- **101**: Weak/vague improvement disclosure; incomplete mechanism; generic implementation language
- **112**: Partial/weak spec support; 112(f) terms with unclear structural linkage; relative terms without clear reference; enablement gaps

### Low Severity (nice to have)
- **101**: Adequate disclosure that could benefit from additional detail; missing secondary benefits
- **112**: Terms clear to POSITA but not explicitly defined; minor scope questions; stylistic indefiniteness

---

# OUTPUT FORMAT

## Section 101 Analysis

### Overall 101 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest 101 risk, or "No significant 101 issues identified"]

### 101 Recommendations

For each recommendation:

**[Number]. [Brief description of the gap]** -- Severity: [High/Medium/Low]

- **Why It Matters:** [How this strengthens 101 position]
- **Where to Add:** [Reference to the section/paragraph in the draft where this should be added]
- **Paste-Ready Language:**
  > [Specification text ready to copy into the draft]

---

## Section 112 Analysis

### Overall 112 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest issue, or "No significant 112 issues identified"]

### 112 Issues

For each issue:

**[Number]. [Issue Type] -- Claims [affected claim numbers]** -- Severity: [High/Medium/Low]

- **Problem:** [Description of the issue]
- **Claim Text:** "[Quote the specific claim text causing the issue]"
- **Remedy:**
  - [If spec change needed] **Add to Specification:**
    > [Paste-ready specification text]
  - [If claim change needed] **Original Claim Text:**
    > [Verbatim original text]
  - [If claim change needed] **Amended Claim Text:**
    > [Paste-ready replacement text]

## Review Summary

| Category | High Severity | Medium Severity | Low Severity | Total |
|---|---|---|---|---|
| 101 Issues | [count] | [count] | [count] | [count] |
| 112(a) Written Description | [count] | [count] | [count] | [count] |
| 112(a) Enablement | [count] | [count] | [count] | [count] |
| 112(b) Indefiniteness | [count] | [count] | [count] | [count] |
| 112(f) Means-Plus-Function | [count] | [count] | [count] | [count] |

**Bottom Line:** [1-2 sentences: Is this draft ready to file, or are there blocking issues?]

---

## IMPORTANT NOTES

- If no issues are found for a section, state "No significant [101/112] issues identified" and provide an empty list
- All recommended language must be paste-ready -- counsels will copy and paste directly into the draft
- For claim amendments, use ONLY vocabulary from the specification (no synonyms or paraphrases)
- For specification additions, you may introduce new framing language to articulate benefits
- Focus on TECHNICAL improvements, not business improvements
- Do NOT suggest quantitative metrics, benchmarks, or performance numbers that would require experimentation
- Do NOT suggest pseudocode, flowcharts, or programming-style syntax -- use patent specification prose
- This is a pre-filing review, so adding new content IS appropriate (no "new matter" concerns)

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_DRAFT}}` | The full patent draft including both the specification (title, background, summary, detailed description, figures) and the claims section |

## Tips

- For best results, include the complete specification and all claims -- the LLM needs both to cross-reference claim elements against specification support.
- The 101 analysis is most relevant for software, business method, and computer-implemented inventions. For purely mechanical or chemical inventions, 101 issues are rare.
- Pay special attention to antecedent basis issues (using "the" without prior introduction) -- these are the most common 112 issues and the easiest to fix.
- The paste-ready remedies are starting points. Always have a patent attorney review the suggested language before incorporating it into the draft.
- For focused analysis of just 101 or just 112, see the separate prompts: [`prompt-101.md`](prompt-101.md) and [`prompt-112.md`](prompt-112.md).

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
