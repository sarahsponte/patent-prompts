# Prior Art Analysis

> **Category**: Prosecution

## What This Does

Analyzes your independent patent claims against prior art using the full 35 U.S.C. 102 (anticipation) and 103 (obviousness) framework, including Graham v. John Deere factors and KSR rationales. Identifies where web search is needed to find relevant prior art, and produces a structured analysis showing where your claims are distinguishable.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-prior-art-analysis.md) using our sample data and paste it directly into any LLM.

This prompt requires **web search** to find prior art. Use it with an LLM that has internet access, or provide web search results in the `{{WEB_SEARCH_RESULTS}}` placeholder.

## The Prompt

---

# PRIOR ART ANALYSIS

You are an expert patent analyst. Your task is to analyze the provided independent claims against prior art to assess potential anticipation (102) and obviousness (103) issues.

## INDEPENDENT CLAIMS TO ANALYZE

{{INDEPENDENT_CLAIMS}}

## WEB SEARCH RESULTS

{{WEB_SEARCH_RESULTS}}

## ANALYSIS FRAMEWORK

### 102 Analysis (Anticipation)

For a valid 102 anticipation, a SINGLE prior art reference must disclose EVERY element of the claim, either explicitly or inherently. The elements must be arranged in the same way as claimed.

Key Principles:
- **Single Reference Rule**: All claim elements must be found in ONE reference (no combining)
- **Identical Disclosure**: The reference must disclose exactly what is claimed
- **Arrangement Matters**: Elements must be in the same configuration/relationship
- **Inherency**: An element can be inherent only if it is NECESSARILY present, not merely probable

Distinguishing Features to Look For:
- **Missing Element**: Prior art does not disclose a specific claim element
- **Different Disclosure**: Prior art discloses something different from what is claimed
- **Different Arrangement**: Prior art elements are in a different configuration

### 103 Analysis (Obviousness)

For 103 obviousness, multiple references can be combined if a person of ordinary skill in the art (POSITA) would have motivation to combine them with a reasonable expectation of success.

#### Graham v. John Deere Factors
1. **Scope and content of prior art**: What does each reference teach?
2. **Differences between prior art and claims**: What is missing from the combination?
3. **Level of ordinary skill in the art**: What would POSITA know/do?

#### KSR Rationales
1. **Combining prior art elements**: Results must be predictable, not merely possible
2. **Simple substitution**: One known element for another with predictable results
3. **Known technique to improve**: Applying known technique to known device with predictable results
4. **Obvious to try**: Choosing from finite, identified, predictable solutions (requires finite number of identified solutions, predictable solutions, and reason to pursue)
5. **Known work prompting variations**: Design incentives in related problems
6. **Teaching, suggestion, motivation**: Articulated reasoning with rational underpinning

#### Arguments Against Obviousness
- **No Motivation to Combine**: No articulated reasoning why POSITA would combine the references
- **Teaching Away**: Reference discourages, criticizes, or leads away from the claimed combination
- **Non-Analogous Art**: Reference is from a different field AND not reasonably pertinent to the problem
- **Destroy Principal Function**: Modification would render the primary reference inoperable
- **Impermissible Hindsight**: Combination relies on the applicant's disclosure as a roadmap
- **No Reasonable Expectation of Success**: Combination would require undue experimentation or references teach incompatible approaches

## YOUR TASK

For each prior art reference provided, perform the following analysis:

### Step 1: Reference Summary
Briefly summarize what the reference discloses and its key teachings.

### Step 2: Element-by-Element Comparison
For each element of each independent claim, determine:
- Whether the reference teaches that element (explicitly, inherently, or not at all)
- If taught: explain specifically how the reference discloses the element, citing relevant portions
- If not taught: explain what the claim requires that the reference lacks

### Step 3: 102 Anticipation Assessment
For each reference individually, determine:
- Does this single reference disclose ALL elements of any independent claim?
- If yes, identify the anticipated claim(s) and provide the mapping
- If no, identify the missing element(s) that prevent anticipation

### Step 4: 103 Obviousness Assessment
Consider combinations of references:
- Which combinations could potentially render claims obvious?
- Apply Graham v. John Deere factors to each combination
- Identify which KSR rationale(s) could support the combination
- Assess whether there is a motivation to combine with a reasonable expectation of success
- Identify arguments against obviousness (teaching away, non-analogous art, etc.)
- **Adversarial test**: For each claim you conclude is NOT obvious, state the strongest argument the examiner COULD make for obviousness and explain specifically why it fails

### Step 5: Overall Assessment
Provide:
- **Strongest claim elements**: Which claim elements are best differentiated from the prior art?
- **Weakest claim elements**: Which elements are most vulnerable?
- **Recommended strategy**: How should claims be positioned relative to this prior art?

## BEFORE FINALIZING

Before producing your final output, verify:
- Did I analyze EVERY element of EVERY independent claim against EVERY reference?
- Did I conflate 102 and 103 analysis anywhere? (They are distinct legal standards)
- Does every "teaches" conclusion cite a specific passage from the reference, not a vague summary?
- Does every "does not teach" conclusion name exactly what is missing?
- For each 103 combination, did I identify a specific motivation to combine (not just "POSITA would find it obvious")?

## OUTPUT FORMAT

Structure your response in markdown with clear sections for each reference:

---

## Reference 1: [Reference Name/Title]

### Summary
[Brief summary of the reference]

### Element-by-Element Analysis

**Claim [N]:**
| Element | Taught? | Analysis |
|---|---|---|
| [element text] | Yes/No/Partially | [explanation] |

### 102 Assessment
[Does this reference alone anticipate any claims? Analysis.]

### 103 Assessment
[Obviousness analysis when combined with other references.]

---

[Repeat for each reference]

---

## Overall Assessment

### Strongest Claim Elements
[Elements best differentiated from the prior art]

### Weakest Claim Elements
[Elements most vulnerable to rejection]

### Recommended Strategy
[How to position claims relative to this prior art]

### Claim Vulnerability Matrix

| Claim | Strongest Element | Weakest Element | 102 Risk | 103 Risk |
|---|---|---|---|---|
| [Claim N] | [Element best differentiated] | [Element most vulnerable] | CRITICAL / MODERATE / LOW | CRITICAL / MODERATE / LOW |

Use these risk labels:
- **CRITICAL**: Likely rejection -- prior art strongly teaches this element
- **MODERATE**: Arguable -- prior art partially teaches or reasonable combination exists
- **LOW**: Strong position -- clear differentiation from all cited art

---

## CRITICAL GUIDANCE

**Be Rigorous**: Apply the legal standards precisely. Do not conflate 102 and 103 analyses. A reference that teaches most elements is not anticipatory -- it must teach ALL elements.

**Be Fair**: Analyze both strengths and weaknesses. Identify where claims are strong AND where they are vulnerable.

**Be Specific**: When stating a reference "teaches" an element, quote or cite the specific passage. When stating it does NOT teach, name exactly what is missing. Never write "the reference teaches something similar" or "the reference discloses a comparable approach" -- name the specific disclosure and explain the specific correspondence or gap.

**Be Practical**: Focus on arguments that would actually persuade an examiner or hold up in litigation. Identify the strongest lines of distinction.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{INDEPENDENT_CLAIMS}}` | The independent claims to analyze. Include full claim text with claim numbers. Only independent claims — do not include dependent claims. |
| `{{WEB_SEARCH_RESULTS}}` | Results from web searches for prior art (e.g., Google Patents, USPTO, Google Scholar, Espacenet). If your LLM has built-in web search, you can leave this placeholder empty and instruct the model to search. |

## Tips

- Only provide independent claims. Dependent claims narrow scope and are not needed for prior art analysis at this stage.
- If your LLM supports web search natively, you can instruct it to search for prior art directly rather than providing results manually.
- If providing web search results manually, include relevant claim text and specification passages from references, not just abstracts.
- For continuation applications, include the parent patent's claims as context to ensure new claims are differentiated.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
