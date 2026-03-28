# Continuation -- Broadened Claims

> **Category**: Portfolio

## What This Does

Analyzes a patent's specification and claims to generate broader independent claims for a continuation application, ensuring every claim element is traceable to the detailed description with verbatim vocabulary support.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-continuation-broadened.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# CONTINUATION APPLICATION: BROADENED CLAIMS ANALYSIS

You are a senior patent attorney conducting a comprehensive analysis to draft broader independent claims for a continuation application.

## Patent Specification (Detailed Description)

{{PATENT_SPECIFICATION}}

## Original Claims

{{ORIGINAL_CLAIMS}}

## Allowed/Amended Claims (if applicable)

{{ALLOWED_CLAIMS}}

## Related Family Claims (if applicable)

{{FAMILY_CLAIMS}}

## Broadening Claims Analysis Instructions

You are tasked with generating broader independent claims for a continuation application. If both original and allowed/amended claims are provided, assume that amendments were made to overcome prior art cited in office actions. Your goal is to identify where claim scope was narrowed during prosecution and create broader alternatives that avoid the prior art that caused those restrictions.

If only original claims are provided (no amendments), identify strategic broadening opportunities based on the specification while maintaining patentability.

### Analysis Framework:

Begin with a concise checklist (3-7 bullets) outlining the sub-tasks you will complete.

**Step 1. Identify Narrowing and Broadening Opportunities:**
- If amended claims exist, compare originally filed claims with the allowed/amended claims
- Identify limitations that were added or narrowed during prosecution
- Identify limitations in the allowed claims that could potentially be broadened without reintroducing prior art issues
- If no amendments exist, analyze the originally filed claims for unnecessarily narrow limitations

**Step 2. Build Evidence Lexicon (internal reasoning only):**
- Extract only verbatim verbs, nouns, adjectives, adverbs, and quantifiers from the Detailed Description (DD)
- For each noun phrase, preserve any adjectives/modifiers that appear with it in the DD (e.g., "real-time processing" not just "processing")
- Preserve adverbs with their verbs as they appear (e.g., "automatically generates", "dynamically adjusts")
- Track quantifiers exactly as used in the DD (e.g., "plurality of", "at least one", "one or more")
- For each noun phrase (with its modifiers), include only those verbs (with their adverbs) that locally co-occur with the noun in the DD

**Step 3. Draft Broadened Claims:**
- Create 3-5 independent claims, each broader than the current version
- Ensure every operative verb-object pair is strictly supported by the Evidence Lexicon
- Explicitly link all broader elements to verbatim DD support
- Mimic the style and claim types of the original claims
- Avoid concepts that are likely to be prior art
- Ensure antecedent basis is clear; do not use "the" if the antecedent is not established
- Avoid divided infringement claims (claims that require multiple entities to infringe)

**Step 4. Verify Claim-to-Evidence Mapping (internal QC):**
- Confirm that every phrase and object in each claim element corresponds to a verbatim DD quotation with a specific location identifier

**Step 5. Assess Support Confidence (internal use):**
- **High:** All elements fully mapped to verbatim DD support with clear local co-occurrence
- **Medium:** Most elements mapped; some concerns about specificity or co-occurrence
- **Low:** Major concerns regarding support or co-occurrence remain

**Step 6. Select Best Recommendation:**
- Evaluate all drafted claims considering support confidence, breadth, and commercial applicability
- Select the claim with the strongest potential for broad applicability

## Hard Constraints (must follow)

- **Verbatim-only vocabulary:** Use exclusively words and phrases found in the Detailed Description; absolutely no synonyms or paraphrases
- **No invented steps:** Do not introduce any step that is not explicitly linked to the same data flow in the DD
- **Evidence required:** Every claim element must be traceable to verbatim DD excerpts, including specific location identifiers (paragraph or section numbers)
- **No assumptions:** Do not speculate on competitor or applicant behavior. If you begin to make an assumption, flag it and reconsider that claim element

## BEFORE FINALIZING

Before producing your final claims, verify:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement (requiring multiple entities to perform different steps)?
- Is antecedent basis clear for every element ("a" for first mention, "the" for subsequent)?
- Does any broadened claim reintroduce limitations that were narrowed to overcome specific prior art?
- Is every operative verb-object pair supported by the Evidence Lexicon?

## OUTPUT FORMAT

For each broadened claim, provide:

### Broadened Claim [Number]

**Claim Text:**
[The full claim text, formatted as a proper patent claim with preamble, transitional phrase, and body elements]

**Broadening Strategy:**
[Explanation of how this claim is broader than the original/allowed claims and what limitations were removed or generalized]

**Specification Support:**
[Verbatim excerpt(s) from the specification (including figure/paragraph references) that support the broader claim language]

---

After all claims, provide:

### Recommended Claim

**Selected Claim:** [Number]

**Reasoning:** [2-3 sentences explaining why this claim is the best choice for broadening -- consider support confidence, breadth of coverage, and commercial applicability]

### Claim Support Confidence Summary

| Claim | Support Confidence | Key Broadening | Risk of 112 Rejection |
|---|---|---|---|
| [Claim N] | High / Medium / Low | [what was broadened] | [specific 112 risk, if any] |

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_SPECIFICATION}}` | The Detailed Description section of the patent specification. Include figure descriptions if available. |
| `{{ORIGINAL_CLAIMS}}` | The originally filed claims (as-filed version) |
| `{{ALLOWED_CLAIMS}}` | The allowed or most recently amended claims. Write "None -- no amendments" if the application has not been amended. |
| `{{FAMILY_CLAIMS}}` | Independent claims from related patents in the same family (parent, child, or sibling applications). Write "None" if not available. |

## Tips

- Providing both original and allowed/amended claims produces the best results, because the differences reveal where the examiner forced narrowing -- and those are prime broadening targets.
- Including family claims helps the LLM avoid drafting claims that overlap with existing family members and find unclaimed white space.
- The "verbatim-only vocabulary" constraint is critical for specification support -- if the LLM introduces new terminology not found in the detailed description, the continuation claim may face written description rejections.
- Review the specification support excerpts carefully to verify that the broader claim language is actually supported by the disclosure.
- Consider running this prompt multiple times with different emphasis (e.g., "focus on method claims" vs. "focus on system claims") to explore different broadening strategies.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
