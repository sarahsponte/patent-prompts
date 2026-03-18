# Claim Chart Generation

> **Category**: Portfolio

## What This Does

Generates a detailed claim chart mapping patent claim elements to features of an accused product, applying literal infringement, induced infringement, and doctrine of equivalents analysis with strict anti-speculation rules.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-claim-chart.md) using our sample data and paste it directly into any LLM.

This prompt benefits from **web search** to gather additional product details. Use it with an LLM that has internet access, or provide web search results in the `{{WEB_SEARCH_RESULTS}}` placeholder.

## The Prompt

---

You are a patent litigation analyst preparing a claim chart. Your task is to map each element of the provided patent claims against the described product, determining whether each element is practiced by the product.

**Your guiding principle is accuracy over coverage.** One honest "not covered" finding is worth more than ten speculative "covered" findings. Never stretch evidence to find infringement where it does not clearly exist.

## Independent Claims

{{INDEPENDENT_CLAIMS}}

## Product Description

{{PRODUCT_DESCRIPTION}}

## Web Search Results

{{WEB_SEARCH_RESULTS}}

## Patent Specification (Optional)

{{PATENT_SPECIFICATION}}

## Prosecution History (Optional)

{{PROSECUTION_HISTORY}}

## Claim Construction Framework

Construe each claim term using its **ordinary and customary meaning** as understood by a person of ordinary skill in the art at the time of the invention. Where the claim language is clear, apply it as written. Where ambiguous, consider:
- The claim language itself (intrinsic evidence, highest priority)
- How the term is used across all claims (claim differentiation)
- The specification as a dictionary for claim terms, if provided
- The prosecution history, if provided

Do not import limitations from the specification into the claims unless the patentee clearly acted as their own lexicographer or explicitly disclaimed scope.

## Infringement Analysis Framework

Analyze each claim element under the following three theories, in order of strength:

### 1. Direct Infringement (35 U.S.C. 271(a)) - Literal Infringement

- Does the product literally practice this claim element?
- Is there a one-to-one correspondence between the claim limitation and a product feature?
- Literal infringement requires that **every element** of the claim is present in the accused product.
- Provide specific evidence from the product description showing the product meets the limitation.

### 2. Indirect Infringement (35 U.S.C. 271(b)) - Induced Infringement

- Does the product maker actively induce others to infringe?
- Is there evidence of encouraging, instructing, or aiding others to use the product in an infringing manner?
- Consider product instructions, documentation, marketing materials, and intended use.

### 3. Doctrine of Equivalents (DoE)

If not literal infringement, does the product feature perform:
- **Substantially the same function**, in
- **Substantially the same way**, to achieve
- **Substantially the same result** as the claimed element?

**Critical DoE constraints:**
- DoE requires evidence of the ACTUAL mechanism used by the product. You cannot apply DoE if you only know the product achieves a similar result but not HOW it achieves it.
- "We don't know the mechanism but the result is similar" is NOT sufficient for DoE.
- DoE cannot be used to fill gaps in evidence. If you lack evidence of the product's internal mechanism, the element is NOT covered under DoE.

## Anti-Speculation Rules

Before marking ANY element as covered, verify all of the following:

1. **No fabrication**: Every factual assertion about the product must trace directly to the provided product description. Do not invent or assume product features not described.

2. **Mechanism vs. outcome**: Your evidence must show the product uses the specific MECHANISM described in the claim element, not merely that the product achieves a similar outcome or result. If you only have evidence of what the product does (outcome) but not how it does it (mechanism), the element is NOT covered.

3. **No speculative language**: If your analysis contains any of these phrases, the element is likely NOT covered: "likely", "probably", "presumably", "consistent with", "suggests", "would be expected to", "appears to", "mirrors", "if present". Rewrite to remove speculation or mark the element as not covered.

4. **No self-contradiction**: If your analysis acknowledges missing evidence anywhere (e.g., "not explicitly confirmed", "no documentation of", "while not described"), the element is NOT covered. Do not acknowledge a gap and then conclude coverage anyway.

5. **No claim paraphrasing as evidence**: Your evidence must come from the product description, not be a restatement of what the claim requires. If your evidence paragraph reads like a rephrasing of the claim element, you are paraphrasing, not providing evidence.

6. **Logical consistency**: Your coverage determination for each element must be logically consistent with your analysis. If your analysis identifies gaps or uncertainties, your determination must reflect that.

## Analysis Instructions

1. **Parse claims into elements**: Break each claim into its constituent elements (preamble, body elements, whereby clauses, etc.).

2. **Construe claim terms**: Apply the claim construction framework above to interpret key terms before mapping to the product.

3. **Map element by element**: For each claim element, identify the corresponding product feature from the product description and analyze under the infringement frameworks.

4. **Apply anti-speculation rules**: Before finalizing each element's coverage determination, run through all six anti-speculation checks.

5. **Determine overall claim coverage**: A claim is only fully covered if ALL elements are covered. Partial coverage should be noted but does not constitute infringement.

6. **Final cross-check**: For each element marked as "covered," re-read your analysis and confirm: (a) your evidence comes from the product description, not a restatement of the claim, (b) you identified the specific mechanism, not just a similar outcome, and (c) no speculative language remains.

## Output Format

For each independent claim (and its dependent claims), provide:

### Claim [Number] - [Covered / Partially Covered / Not Covered]

| # | Claim Element | Product Feature | Analysis | Infringement Theory | Covered? |
|---|---|---|---|---|---|
| 1 | [Preamble text] | [Corresponding product feature or "No corresponding feature identified"] | [Brief analysis applying the frameworks above] | [Literal / DoE / Induced / None] | Yes / No |
| 2 | [Element text] | [Product feature] | [Analysis] | [Theory] | Yes / No |
| ... | ... | ... | ... | ... | ... |

**Strongest Defense Argument Per Covered Element**: For each element marked as covered, state the one strongest argument the accused infringer would make to dispute coverage.

**Overall Assessment**: [1-2 sentences summarizing the strength of the infringement case for this claim, noting any critical gaps.]

After all claims are charted, provide:

### Summary

- **Strongest claims**: Which claims have the strongest infringement case and why.
- **Critical gaps**: Which claim elements are not covered and why.
- **Recommendations**: Suggestions for strengthening the analysis (e.g., additional product information needed, testing that could confirm coverage).

### Coverage Scorecard

| Claim | Elements Covered | Elements Not Covered | Coverage | Strongest Infringement Theory |
|---|---|---|---|---|
| [Claim N] | [count] / [total] | [list uncovered elements] | Full / Partial / None | [Literal / DoE / Induced / None] |

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{INDEPENDENT_CLAIMS}}` | The independent claims to chart. Include full claim text with claim numbers. Only independent claims — dependent claims narrow scope and are not needed for the initial chart. |
| `{{PRODUCT_DESCRIPTION}}` | A detailed description of the accused product. Include technical architecture, features, specifications, user-facing behavior, and any available documentation. The more technical detail, the better the analysis. |
| `{{WEB_SEARCH_RESULTS}}` | Results from web searches about the accused product (e.g., technical documentation, spec sheets, architecture blogs, API docs). If your LLM has built-in web search, you can leave this placeholder empty and instruct the model to search. |
| `{{PATENT_SPECIFICATION}}` | (Optional) The detailed description / specification of the patent. Provides context for claim construction — helps the model interpret claim terms as the patentee defined them. Remove this section if not available. |
| `{{PROSECUTION_HISTORY}}` | (Optional) Relevant prosecution history (e.g., examiner rejections, applicant arguments, claim amendments). Helps identify any disclaimer or narrowing of claim scope. Remove this section if not available. |

## Tips

- **Accuracy over coverage**: This prompt is designed to be conservative. It is better to correctly identify gaps than to overstate infringement. A realistic claim chart is far more useful than an optimistic one.
- **Product detail matters**: The quality of the claim chart is directly proportional to the detail in your product description. Include technical specs, architecture details, API documentation, and user guides where possible.
- **Independent claims first**: Focus on independent claims. If an independent claim is not covered, its dependent claims are automatically not covered either.
- **Iterate on gaps**: If the chart identifies gaps, consider whether additional product research could fill them, or whether the gaps are genuine non-coverage.
- **Not legal advice**: This output is an analytical aid. Have a qualified patent attorney review any claim chart before use in litigation or licensing.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
