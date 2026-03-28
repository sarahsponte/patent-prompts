# Continuation -- Unclaimed Subject Matter

> **Category**: Portfolio

## What This Does

Analyzes a patent's specification to identify disclosed subject matter that was never claimed, either in the original patent or across the patent family. Generates continuation claims for the most commercially valuable unclaimed disclosures, with full written description support.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-continuation-unclaimed.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# CONTINUATION APPLICATION: UNCLAIMED SUBJECT MATTER ANALYSIS

You are a senior patent attorney mining a patent specification for valuable subject matter that was disclosed but never claimed. Your task is to identify unclaimed disclosures and draft continuation claims to capture them.

## Patent Specification (Detailed Description)

{{PATENT_SPECIFICATION}}

## Current Claims

{{CURRENT_CLAIMS}}

## Family Claims (if applicable)

{{FAMILY_CLAIMS}}

## Hard Constraints

- **Verbatim-only vocabulary**: Use ONLY words and phrases that appear in the Detailed Description (DD). Do not use synonyms, paraphrases, or terminology not found in the specification.
- **No invented steps**: Do not introduce any method step or system component unless the DD explicitly describes it in the relevant context.
- **Evidence required**: Every claim element must be traceable to a specific verbatim excerpt from the DD. You must provide the supporting excerpt for each element.
- **No assumptions**: Do not infer features or capabilities beyond what is explicitly described in the specification. If you find yourself making an assumption, flag it and reconsider.

## Analysis Process

Follow these steps in order. Show your work for each step.

### Step 1: Specification Mining

Systematically read the Detailed Description and identify all disclosed technical concepts, methods, systems, components, and embodiments. For each, note:
- What is disclosed (the technical concept or feature)
- Where it is disclosed (paragraph/section reference)
- The level of detail provided (fully described vs. briefly mentioned)

### Step 2: Coverage Gap Analysis

Compare the mined disclosures against all provided claims (current claims and family claims). Identify subject matter that is:
- **Fully unclaimed**: Disclosed in the specification but not covered by any claim in the family
- **Partially unclaimed**: The general concept is claimed, but specific embodiments or aspects are not
- **Unclaimed combinations**: Individual elements may be claimed separately, but a disclosed combination of them is not

Exclude from consideration:
- Subject matter that is clearly anticipated by well-known prior art
- Trivial implementation details that would not provide meaningful claim scope
- Subject matter that lacks sufficient detail in the specification to support a claim

### Step 3: Commercial Value Assessment

For each unclaimed disclosure, assess:
- **Breadth potential**: Could this support a broad independent claim, or only narrow dependent claims?
- **Industry relevance**: Is this the kind of feature competitors are likely implementing or will implement?
- **Enforceability**: Could infringement of a claim to this subject matter be detected from publicly observable behavior or products?
- **Specification support depth**: Is there enough detail in the DD to draft a robust claim that would survive a 112 challenge?

Rank the unclaimed disclosures by overall commercial value.

### Step 4: Evidence Lexicon

For the top 3-5 unclaimed disclosures, build a vocabulary lexicon extracted verbatim from the DD:
- **Nouns/noun phrases**: Preserve all adjectives and modifiers as they appear
- **Verbs/verb phrases**: Preserve adverbs as they appear
- **Quantifiers**: Use exactly as they appear (e.g., "plurality of", "at least one")
- **Co-occurrence pairs**: For each noun phrase, list only the verbs that appear with it in the DD

### Step 5: Draft Continuation Claims

For each of the top 3-5 unclaimed disclosures, draft an independent claim:
- Use only vocabulary from the Evidence Lexicon
- Ensure every operative verb-object pairing comes directly from DD co-occurrence
- Draft at the broadest scope supportable by the specification
- Ensure proper antecedent basis
- Avoid divided infringement
- Include 2-3 dependent claims per independent claim that add meaningful fallback positions

### Step 6: Verify Support

For each claim, confirm:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement?
- Is antecedent basis clear for every element?
- Is every operative verb-object pair supported by the Evidence Lexicon?
- Is this subject matter genuinely unclaimed by the existing family?

## Output Format

### Specification Mining Summary

A table of all identified disclosures:

| # | Disclosed Subject Matter | Location in DD | Claimed? | Notes |
|---|---|---|---|---|
| 1 | [description] | [paragraph/section] | No / Partial / Yes | [brief note] |

### Top Unclaimed Disclosures

For each of the top 3-5 unclaimed disclosures, ranked by commercial value:

#### [Rank]. [Disclosure Name]

**What was disclosed:** [description of the unclaimed subject matter]

**Where disclosed:** [specific DD location(s)]

**Why it was likely never claimed:** [your assessment -- e.g., prosecution narrowed focus elsewhere, examiner pressure on other claims, applicant prioritized different aspects]

**Commercial value:** [assessment of breadth, industry relevance, and enforceability]

### Proposed Continuation Claims

For each disclosure:

#### Claims for: [Disclosure Name]

**Independent Claim [N]:**
[Full claim text]

**Dependent Claims:**
[Dependent claim texts]

**Specification Support:**

| Claim Element | Verbatim DD Support | Location |
|---|---|---|
| [element] | [exact quote] | [paragraph/section] |

**Support Confidence:** High / Medium / Low

### Recommendation

**Priority filing order:** [Rank the proposed claims by which should be filed first, with reasoning]

### Summary

| Disclosure | Claim Type | Support Confidence | Breadth | Industry Relevance | Priority |
|---|---|---|---|---|---|
| [name] | Method / System / CRM | High / Med / Low | Broad / Moderate / Narrow | High / Med / Low | [1-5] |

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_SPECIFICATION}}` | The full Detailed Description section of the patent specification. Include figure descriptions. |
| `{{CURRENT_CLAIMS}}` | All claims of the patent (independent and dependent) |
| `{{FAMILY_CLAIMS}}` | Independent claims from related patents in the same family (parent, child, sibling applications). Write "None" if not available or if this is a standalone patent. |

## Tips

- Including family claims is especially important for this prompt. Without them, the analysis may flag subject matter as "unclaimed" when it is already covered by a related patent.
- The more complete the Detailed Description, the better. Figures and their descriptions often contain disclosed embodiments that were never claimed.
- This analysis works best on patents with rich specifications that describe multiple embodiments or use cases beyond what the claims cover.
- Pay attention to the "Why it was likely never claimed" assessment. Subject matter that was never claimed because it lacks novelty is different from subject matter that was simply overlooked during prosecution.
- Consider running the output claims through the [Claim Chart](../claim-chart/prompt.md) prompt against a competitor product to validate commercial relevance.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
