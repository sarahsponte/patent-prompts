# Patent Pruning Analysis

> **Category**: Portfolio

## What This Does

Evaluates whether a patent case should be maintained or pruned based on claim scope analysis relative to other cases in the same patent family, producing a determination of BROADEST, COMPLEMENTARY, NARROW, SUNSET, or REVIEW with supporting reasoning.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-pruning-analysis.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# PATENT PRUNING FAMILY ANALYSIS

## Context

You are a patent portfolio analyst evaluating whether a patent case should be maintained or pruned based on claim scope analysis relative to other cases in the same patent family.

## Target Case for Analysis

- Docket Number: {{TARGET_DOCKET}}
- Country: {{TARGET_COUNTRY}}
- Status: {{TARGET_STATUS}}
- Years Remaining: {{TARGET_YEARS_REMAINING}}
- First Independent Claim:
{{TARGET_FIRST_INDEPENDENT_CLAIM}}

## Other Cases in Same Jurisdiction ({{TARGET_COUNTRY}})

{{SAME_JURISDICTION_CASES}}

## Other Cases in Extended Family (Other Jurisdictions)

{{OTHER_JURISDICTION_CASES}}

## Instructions

Analyze the target case's first independent claim against other ALIVE cases in the SAME jurisdiction only. Consider both claim scope AND remaining patent life.

### Determination Criteria (evaluate in this order):

**REVIEW** -- Return this FIRST if:
- Target case is "Pending (published application)" -- these are not yet issued and cannot be classified by claim scope
- Comparison is uncertain (complex claim language)
- Claims have overlapping but partially distinct coverage that is hard to categorize
- Missing claim data prevents analysis
- Edge case requiring human judgment

**SUNSET** -- Return this if:
- Target case is "Issued (enforceable)" AND has less than 3 years remaining patent life
- Note: SUNSET only applies to issued patents, never to pending applications
- Note in reasoning whether coverage is maintained by longer-lived cases in the jurisdiction

**BROADEST** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- AND one of:
  - No other ALIVE cases exist in the same jurisdiction
  - Target claim is the BROADEST among all alive cases in this jurisdiction (fewest limitations, covers most embodiments)

**COMPLEMENTARY** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- Target claim covers DISTINCT subject matter not covered by any other alive case (e.g., different apparatus vs method, different technical approach)
- The claim is not simply narrower -- it covers genuinely different aspects

**NARROW** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- At least one other ALIVE case exists in the same jurisdiction
- AND one of:
  - Target claim is NARROWER than another alive case (adds more limitations, covers subset of embodiments)
  - Target claim has DUPLICATE/EQUIVALENT scope to another alive case

### Analysis Guidelines:
- A claim is "broader" if it covers more embodiments with fewer limitations
- A claim is "narrower" if it adds specific limitations that reduce scope
- "Complementary" means genuinely different coverage (e.g., method vs apparatus, different inventive concept), NOT just a narrower version
- Consider both apparatus and method claim distinctions
- Status is evaluated FIRST -- a pending (published) application is always REVIEW regardless of scope
- Age is evaluated SECOND -- an issued case with less than 3 years is SUNSET regardless of scope
- If target case has no claims available, return REVIEW with appropriate reasoning

## OUTPUT FORMAT

### Determination: [BROADEST / COMPLEMENTARY / NARROW / SUNSET / REVIEW]

**Reasoning:** [2-3 sentences explaining your determination. Refer to the target case as "this case" and reference other cases by their docket numbers. Describe the factual basis for your analysis -- years remaining, claim scope comparisons, etc.]

**Broader Cases in Jurisdiction:** [List docket numbers of cases with broader claims than the target in the same country. Write "None" if target is broadest or complementary.]

### Recommendation

[1-2 sentences on the portfolio action: maintain, consider abandoning, flag for attorney review, etc.]

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{TARGET_DOCKET}}` | Internal docket number of the case being analyzed |
| `{{TARGET_COUNTRY}}` | ISO country code (e.g., USA, DEU, JPN) |
| `{{TARGET_STATUS}}` | Status of the case: "Issued (enforceable)" or "Pending (published application)" |
| `{{TARGET_YEARS_REMAINING}}` | Years of patent life remaining (e.g., "12.3"). Write "Unknown" if not available. |
| `{{TARGET_FIRST_INDEPENDENT_CLAIM}}` | Full text of the first independent claim. Write "No claims available" if claims are not accessible. |
| `{{SAME_JURISDICTION_CASES}}` | List of other cases in the same jurisdiction. For each case, include: Docket, Status, Years Remaining, and First Independent Claim. Write "No other cases in this jurisdiction." if none exist. |
| `{{OTHER_JURISDICTION_CASES}}` | List of family cases in other jurisdictions. For each, include: Docket, Country, Status, Years Remaining, and First Independent Claim. Write "None" if not applicable. |

## Tips

- For each case in the same jurisdiction and other jurisdictions, use this format:
  ```
  - Docket: ABC-123 | Status: Issued (enforceable) | Years Remaining: 8.5
    First Independent Claim: A method for processing data comprising...
  ```
- The analysis focuses on same-jurisdiction comparisons because patent rights are territorial. Other jurisdiction cases provide family context but do not drive the pruning determination.
- NARROW determinations are the strongest candidates for pruning -- they indicate redundant coverage that is already provided by a broader case in the same jurisdiction.
- SUNSET cases should be evaluated for whether their coverage is maintained by longer-lived family members before deciding to abandon.
- Run this analysis across all cases in a patent family to get a complete picture of which cases to maintain and which to prune.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
