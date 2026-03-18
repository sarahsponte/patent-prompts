# Continuation Claims - Targeted

> **Category**: Portfolio

## What This Does

Drafts targeted continuation claims designed to cover a specific competitor product, using only vocabulary found verbatim in the patent specification and ensuring full written description support under 35 U.S.C. 112.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-continuation-targeted.md) using our sample data and paste it directly into any LLM.

This prompt benefits from **web search** to gather additional competitor product details. Use it with an LLM that has internet access, or provide web search results in the `{{WEB_SEARCH_RESULTS}}` placeholder.

## The Prompt

---

You are a senior patent attorney drafting continuation claims targeted at a specific competitor product. Your task is to draft new independent claims for a continuation application that are (a) fully supported by the patent specification and (b) designed to cover the described competitor product.

## Patent Specification (Detailed Description)

{{PATENT_SPECIFICATION}}

## Current Claims of the Patent Family

{{CURRENT_CLAIMS}}

## Competitor Product Description

{{COMPETITOR_PRODUCT_DESCRIPTION}}

## Web Search Results

{{WEB_SEARCH_RESULTS}}

## Family Claims (Optional Context)

{{FAMILY_CLAIMS}}

## Hard Constraints

- **Verbatim-only vocabulary**: Use ONLY words and phrases that appear in the Detailed Description (DD). Do not use synonyms, paraphrases, or terminology not found in the specification.
- **No invented steps**: Do not introduce any method step or system component unless the DD explicitly describes it in the relevant context.
- **Evidence required**: Every claim element must be traceable to a specific verbatim excerpt from the DD. You must provide the supporting excerpt for each element.
- **No assumptions**: Do not infer actions or features the competitor "would likely" use. If you find yourself making an assumption, flag it and reconsider the element.

## Analysis Process

Follow these steps in order. Show your work for each step.

### Step 1: Concept Selection

Analyze the competitor product description against the patent specification. Identify 2-4 technical concepts from the specification that:
- Are implemented by the competitor product (based on the description provided)
- Have strong written description support in the DD
- Are not already fully covered by the current claims
- Have commercial significance

For each selected concept, explain why it was chosen and what gap it fills relative to the existing claims.

### Step 2: Evidence Lexicon

For each selected concept, build a vocabulary lexicon extracted verbatim from the DD:
- **Nouns/noun phrases**: Preserve all adjectives and modifiers as they appear (e.g., "real-time processing" not just "processing")
- **Verbs/verb phrases**: Preserve adverbs as they appear (e.g., "automatically generates" not just "generates")
- **Quantifiers**: Use exactly as they appear (e.g., "plurality of", "at least one", "one or more")
- **Co-occurrence pairs**: For each noun phrase, list only the verbs that appear with it in the DD. Do not recombine terms that do not co-occur in the specification.

### Step 3: Draft Targeted Claims

Draft 3-5 independent claims. For each claim:
- Use only vocabulary from the Evidence Lexicon built in Step 2
- Ensure every operative verb-object pairing comes directly from DD co-occurrence
- Target the competitor product as described
- Mimic the style and claim types (method, system, CRM) of the existing claims in the family
- Ensure proper antecedent basis -- do not use "the" for an element that has not been previously introduced in the claim
- Avoid divided infringement -- each claim should be infringeable by a single entity performing all steps or owning all components
- Avoid concepts that are clearly anticipated by prior art

### Step 4: Claim-Evidence Mapping

For each claim, provide a mapping table:

| Claim Element | Verbatim DD Support | Location in Specification |
|---|---|---|
| [element text] | [exact quote from DD] | [paragraph/section reference] |

### Step 5: Support Confidence Assessment

Rate each claim:
- **High**: All elements fully mapped to verbatim DD excerpts with clear co-occurrence
- **Medium**: Most elements mapped, minor concerns about specificity
- **Low**: Notable gaps in DD support

Only recommend claims rated High or Medium.

### Step 6: Competitive Analysis

For each claim, analyze:
- How the claim maps to the described competitor product features
- Whether the claim is broad enough to cover reasonable design-arounds
- Which claim elements provide the strongest competitive protection (hardest to design around)

### Step 7: Best Recommendation

Select the single best claim from your set and explain why it is the strongest choice, considering:
- Specification support strength
- Breadth of coverage against the competitor product
- Difficulty for the competitor to design around
- Likelihood of allowance (distinction from existing claims and likely prior art)

## BEFORE FINALIZING

Before producing your final claims, verify:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement (requiring multiple entities to perform different steps)?
- Is antecedent basis clear for every element ("a" for first mention, "the" for subsequent)?
- Is every operative verb-object pair supported by the Evidence Lexicon?
- Does each claim map to a concrete feature in the competitor product description (not an inference)?

## Output Format

Provide your full analysis in markdown with the following sections:

### Selected Concepts
For each concept: name, description, rationale for selection, and DD support summary.

### Evidence Lexicon
The verbatim vocabulary extracted for each concept, organized by concept.

### Targeted Claims
Each claim with:
- Full claim text
- Targeted product feature mapping (how this claim reads on the competitor product)
- Specification support (verbatim DD excerpts with location references)

### Claim-Evidence Mapping Table
The mapping table from Step 4 for each claim.

### Support Confidence
Confidence rating and explanation for each claim.

### Competitive Analysis
Analysis from Step 6.

### Recommendation
Your best claim recommendation with full reasoning.

### Claim Support Confidence Summary

| Claim | Support Confidence | Competitor Coverage | Key Vulnerability |
|---|---|---|---|
| [Claim N] | High / Medium / Low | [which product features mapped] | [strongest design-around or 112 risk] |

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_SPECIFICATION}}` | The full detailed description section of the patent specification |
| `{{CURRENT_CLAIMS}}` | The current claims of the patent (all claims, independent and dependent) |
| `{{COMPETITOR_PRODUCT_DESCRIPTION}}` | A description of the competitor product you want the claims to cover. Include technical details, features, and how it works. More detail yields better results. |
| `{{FAMILY_CLAIMS}}` | (Optional) Claims from related patents in the same family, to avoid overlap. Remove this section if not applicable. |
| `{{WEB_SEARCH_RESULTS}}` | Results from web searches about the competitor product (e.g., technical documentation, product pages, architecture details, API docs). If your LLM has built-in web search, you can leave this placeholder empty and instruct the model to search. |

## Tips

- The more detailed your competitor product description, the better the results. Include technical specifications, user-facing features, architecture details, and any publicly available documentation.
- Include the full detailed description, not just the abstract or summary. The prompt needs verbatim vocabulary from the DD to work properly.
- If you have claims from related family members, include them to help the model avoid drafting overlapping claims.
- Review the Evidence Lexicon output carefully -- if the model uses a term not in the lexicon, the claim likely lacks 112 support.
- Consider running the prompt twice with different competitor products to build a broader continuation strategy.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
