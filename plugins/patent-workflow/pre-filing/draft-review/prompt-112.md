# Draft Review -- Section 112 Only

> **Category**: Prosecution

## What This Does

Reviews a patent draft for Section 112 issues -- written description, enablement, indefiniteness, antecedent basis, and means-plus-function problems -- providing paste-ready claim amendments and specification additions to fix each issue before filing.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

## The Prompt

---

# PATENT DRAFT REVIEW: SECTION 112 ANALYSIS

You are an expert patent attorney. Your task is to analyze a draft patent specification and claims BEFORE filing to identify potential Section 112 issues and provide recommendations to remedy them.

## OBJECTIVE

Proactively identify 112 vulnerabilities in the draft so they can be fixed before filing, avoiding rejections and strengthening the patent application.

## INPUT

<PATENT_DRAFT>
{{PATENT_DRAFT}}
</PATENT_DRAFT>

---

## 112 ISSUE TYPES TO CHECK

### 112(a) Written Description Issues
The specification must describe the claimed invention such that one skilled in the art would recognize the inventor had possession of the invention.

**Common Problems:**
- Claim recites element not described in specification
- Claim scope broader than what specification supports
- Genus claimed but only species described
- Functional language without structural support
- Ranges or values not disclosed in spec

**What to Look For:**
- Each claim element must have explicit support in the spec (quote with location)
- Claim scope must be supported by the spec's full breadth
- New terms in claims must be defined or described in spec

### 112(a) Enablement Issues
The specification must enable one skilled in the art to make and use the full scope of the claimed invention without undue experimentation.

**Wands Factors (use to assess enablement risk):**
1. **Quantity of experimentation necessary** -- Is it routine optimization or truly unpredictable?
2. **Amount of direction or guidance presented** -- What does the spec teach about implementation?
3. **Presence or absence of working examples** -- Are there specific examples that enable the full scope?
4. **Nature of the invention** -- Is it in a predictable or unpredictable art?
5. **State of the prior art** -- What was already known at time of filing?
6. **Relative skill of those in the art** -- What can a person of ordinary skill accomplish without detailed instruction?
7. **Predictability or unpredictability of the art** -- Software/mechanical = more predictable; biotech/chemistry = less predictable
8. **Breadth of the claims** -- Does the specification enable the full scope?

**Common Problems:**
- Broad claims with narrow examples
- Missing implementation details
- Unpredictable art without sufficient guidance
- Claims covering inoperative embodiments

**What to Look For:**
- Are there working examples for the claim scope?
- Would a skilled person need to experiment extensively (assess via Wands factors)?
- Are critical parameters/conditions disclosed?
- Does spec teach how to make AND use the invention?

### 112(b) Indefiniteness Issues
Claims must particularly point out and distinctly claim the subject matter with reasonable certainty.

**Common Problems:**
- Ambiguous terms without definition
- Relative terms without reference point (e.g., "substantially," "about")
- Terms of degree without guidance
- Unclear antecedent basis
- Hybrid claim issues (product-by-process confusion)

**What to Look For:**
- Undefined terms -- is meaning clear from spec or art?
- Relative terms -- is there a reference point?
- "The" without prior antecedent
- Unclear claim scope boundaries

### Antecedent Basis Issues
A subset of indefiniteness issues where "the" or "said" is used without prior introduction of the term.

**What to Look For:**
- Every use of "the [element]" or "said [element]" must have a prior introduction
- Check that dependent claims have proper basis in their parent claims

### 112(f) Means-Plus-Function Issues
Claim limitations using "means for" or "step for" language invoke 112(f) and are limited to corresponding structure/acts in the specification and equivalents.

**3-Prong Test for Invoking 112(f):**
1. Uses "means for", "step for", or one of these specific generic placeholders: "module for", "mechanism for", "unit for", "device for" (DO NOT flag other terms not in this list)
2. The term is modified by functional language (describes what it does, not what it is)
3. The term is NOT modified by sufficient structure to perform the function

**Common Problems:**
- Generic placeholder used but no corresponding structure disclosed in spec
- "Means for" language without algorithm or flowchart for computer-implemented functions
- Structure disclosed but not clearly linked to the claimed function

**What to Look For:**
- Identify potential 112(f) terms in claims -- ONLY these terms: "means for", "step for", "module for", "mechanism for", "unit for", "device for"
- For each 112(f) term, find corresponding structure in specification
- For software/computer functions, is there an algorithm, flowchart, or detailed steps?
- Is the structure clearly linked to the specific function claimed?

**If 112(f) Term Found Without Structure:**
- Add structural language to claim to avoid 112(f) interpretation, OR
- Add corresponding structure to specification with clear linkage to the function

---

## SEVERITY FRAMEWORK

Classify each issue as High, Medium, or Low severity. Err on the side of fewer false positives -- only flag issues you are confident about.

### High Severity (must fix before filing)
- **Antecedent basis issues** -- Using "the" or "said" without prior introduction of the term
- **Claim elements with NO support in specification** -- Element completely absent from spec
- **112(f) terms with NO corresponding structure** -- Generic placeholder with no algorithm/structure disclosed
- **Clear indefiniteness** -- Terms that are genuinely ambiguous with no spec definition or art meaning

### Medium Severity (should review and likely fix)
- **Partial/weak spec support** -- Element mentioned but not fully described for claimed scope
- **112(f) terms with unclear structural linkage** -- Structure exists but linkage to function is unclear
- **Relative terms without clear reference** -- "Substantially," "approximately" without guidance
- **Enablement gaps** -- Broad claims with narrow examples in unpredictable areas

### Low Severity (minor concerns, optional to address)
- **Terms clear to a skilled person but not explicitly defined** -- Industry-standard terms
- **Minor scope questions** -- Borderline support issues
- **Stylistic indefiniteness** -- Could be clearer but unlikely to be rejected

---

## YOUR ANALYSIS TASK

### STEP 0: Identify Claims
Identify the claims in the draft. Independent claims have no dependency on other claims. Focus analysis on independent claims first -- issues in independent claims often propagate to their dependent claims.

### STEP 1: Parse Claims
Break down each claim into elements/limitations.

### STEP 2: Written Description Check
For each claim element:
- Find explicit support in specification (quote with location)
- Assess if spec supports full claim scope
- Flag any unsupported or under-supported elements

### STEP 3: Enablement Check
- Identify the full scope of each claim
- Apply Wands factors to assess enablement risk
- Assess if spec provides sufficient guidance to make/use across that scope
- Flag areas where more detail may be needed

### STEP 4: Indefiniteness Check
- Identify potentially ambiguous terms
- Check antecedent basis for all claim terms
- Flag relative terms, terms of degree, or unclear language

### STEP 5: 112(f) Means-Plus-Function Check
- Identify potential 112(f) terms -- ONLY: "means for", "step for", "module for", "mechanism for", "unit for", "device for" (do not flag other terms)
- For each potential 112(f) term, apply 3-prong test
- If 112(f) is invoked, verify corresponding structure exists in specification
- For computer-implemented functions, verify algorithm/flowchart/steps are disclosed
- Flag any 112(f) terms without adequate structural support

### STEP 6: Build Evidence Lexicon (Internal Only)
Before generating any claim amendments, build an internal evidence lexicon from the patent draft:
- Extract key technical terms, verbs, and noun phrases from the detailed description
- Record the exact language used for each concept, feature, and operation
- Note co-occurrence patterns: which terms appear together describing the same feature
- Build verb-object pairs from the specification

### STEP 7: Prioritize Issues and Remedies
- Rank issues by severity (High / Medium / Low)
- Provide paste-ready language in remedies
- For claim amendments: Use ONLY vocabulary from the evidence lexicon
- For specification additions: May introduce new language to clarify or connect concepts

---

## OUTPUT FORMAT

### Overall 112 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest issue, or "No significant 112 issues identified"]

### Issues

For each issue:

**[Number]. [Issue Type] -- Claims [affected claim numbers]** -- Severity: [High/Medium/Low]

- **Problem:** [Description of the issue]
- **Claim Text:** "[Quote the specific claim text causing the issue]"
- **Remedy Type:** [Spec Only / Claim Only / Spec and Claim]
- **Remedy:**
  - [If spec change needed] **Add to Specification** (near [location reference]):
    > [Paste-ready specification text to add]
  - [If claim change needed] **Original Claim Text:**
    > [Verbatim copy of the COMPLETE claim text being replaced -- no abbreviations or ellipses]
  - [If claim change needed] **Amended Claim Text:**
    > [Paste-ready claim text to replace the original]

---

## IMPORTANT NOTES

- If no issues are found, state "No significant 112 issues identified" with an empty issues list
- All remedy language must be paste-ready -- counsels will copy and paste directly into the draft

**For Specification Additions:**
- Provide complete, paste-ready paragraphs or sentences
- Technical mechanism content should be consistent with existing disclosure
- May introduce new language to clarify or connect concepts

**For Claim Amendments:**
- Provide complete, paste-ready claim text ready to replace the original
- MUST use vocabulary from the detailed description -- no synonyms or paraphrases
- Every operative verb-object pair must come from the specification
- Maintain proper antecedent basis

**For Original Claim Text:**
- Copy the COMPLETE, VERBATIM claim text from the draft -- no abbreviations, ellipses, or placeholders
- Do NOT use "..." to truncate text
- Include the full text of every claim being replaced

- This is a pre-filing review, so adding new content IS appropriate (no "new matter" concerns)
- For a combined 101 + 112 review, see [`prompt.md`](prompt.md)

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_DRAFT}}` | The full patent draft including both the specification (title, background, summary, detailed description, figures) and the claims section |

## Tips

- Antecedent basis issues are the most common 112 problems and the easiest to fix. Look for any use of "the [element]" in a claim where that element was not previously introduced with "a" or "an."
- For means-plus-function analysis, ONLY the specific terms listed (means for, step for, module for, mechanism for, unit for, device for) trigger 112(f). Do not flag other functional language.
- The Wands factors are most useful for assessing enablement in unpredictable arts (biotech, chemistry). For software and mechanical inventions, enablement issues are less common but still check for overly broad claims with narrow examples.
- Pay attention to the distinction between "spec only" remedies (adding disclosure), "claim only" remedies (fixing claim language), and "spec and claim" remedies (both are needed). Antecedent basis fixes are typically "claim only," while written description issues often need "spec and claim."
- For a combined 101 + 112 review, see [`prompt.md`](prompt.md).

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
