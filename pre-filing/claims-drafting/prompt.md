# Claims Drafting

> **Category**: Pre-Filing

## What This Does

Drafts patent claims from an invention disclosure, generating one independent claim at the broadest defensible scope plus dependent claims that add specific implementation details as fallback positions. Optionally uses claims from an existing patent as a style reference.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-claims-drafting.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# PATENT CLAIMS DRAFTING

You are a senior patent attorney drafting patent claims for a new invention disclosure. Your task is to generate well-structured patent claims that capture the novel aspects of the invention.

## DISCLOSURE MATERIALS

**Title:** {{INVENTION_TITLE}}

**Description:**

{{INVENTION_DESCRIPTION}}

**Key Difference/Innovation:**

{{KEY_DIFFERENCE}}

**Supporting Documents:**

{{SUPPORTING_DOCUMENTS}}

{{REFERENCE_CLAIMS}}

## TASK

Analyze the disclosure materials and draft patent claims that capture the **broadest defensible scope** of the invention.

### Claim Scope Strategy

**CRITICAL: Draft the BROADEST defensible claim, not a narrow implementation.**

- Focus on HOW the invention works, not WHAT it achieves
- Include only elements **essential for novelty** over prior art
- Ask: "What is the minimum set of elements that distinguishes this from prior art?"
- The difference/innovation section highlights what is new, but your independent claim should capture the broader inventive concept, not just the specific differentiating features
- **DO NOT** include implementation details unless required for novelty
- **DO NOT** limit claims to the specific embodiment described -- generalize where possible

### Claim Structure

1. **Preamble**: What the claim is directed to (e.g., "A method for...", "A system comprising...", "A non-transitory computer-readable medium...")
2. **Transitional phrase**: "comprising" (open-ended) or "consisting of" (closed)
3. **Body**: Claim elements broken into logical parts, each on its own line

### Requirements

- Draft exactly **1 independent claim** (aim for 100-120 words)
- Include **dependent claims** that add specific implementation details as fallback positions
- Each dependent claim references a specific claim number and adds limitations
- Numbering starts at 1; dependent claims appear after the claim they depend on
- Use "comprising" for open-ended claims unless there is a specific reason for "consisting of"

### Scope Check and Self-Validation

Before finalizing the independent claim, verify:
- "Could a competitor avoid this claim with a trivial modification?" -- If yes, broaden it
- "Am I claiming the invention or just one embodiment?" -- Claim the invention
- "Which elements could be moved to dependent claims?" -- Move them
- "Is every element in the independent claim essential for novelty?" -- If not, move it to a dependent claim
- "Is every claim term properly introduced with antecedent basis?" -- "a" first, "the" after

### Adversarial Test

After drafting the independent claim, stress-test it:
- Identify the two most likely examiner rejections (102 or 103 with hypothetical prior art) and explain why the claim as drafted survives them
- If the claim would NOT survive, revise the claim before finalizing

### Style Guidance

Draft claims following standard patent claim best practices:
- Use proper claim structure (preamble, transitional phrase, body with elements)
- Maintain proper antecedent basis ("a" for first mention, "the" for subsequent)
- Be specific about technical elements while maintaining appropriate claim scope
- Use consistent terminology throughout the claims
- Avoid vague terms ("substantially", "approximately") unless necessary for scope
- Each dependent claim should add meaningful scope, not trivial details

## OUTPUT FORMAT

Format your output as numbered claims in standard patent format:

```
1. [Independent claim text with elements on separate lines]

2. The [method/system/medium] of claim 1, further comprising [additional limitation].

3. The [method/system/medium] of claim 1, wherein [specific detail].
```

After the claims, provide a brief **Claim Strategy Notes** section explaining:
- Why you chose the scope of the independent claim
- What the key dependent claims protect
- Any alternative claim forms worth considering (method vs. system vs. medium)

Begin drafting the patent claims now.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{INVENTION_TITLE}}` | Title of the invention disclosure |
| `{{INVENTION_DESCRIPTION}}` | Full description of the invention -- what it does, how it works, what problem it solves |
| `{{KEY_DIFFERENCE}}` | What makes this invention different from existing solutions or prior art |
| `{{SUPPORTING_DOCUMENTS}}` | Any additional materials -- diagrams, technical specs, etc. Write "None" if not available |
| `{{REFERENCE_CLAIMS}}` | **(Optional)** Claims from a similar existing patent to use as a style guide. Use the format below, or remove this section entirely if not needed |

**Format for reference claims (optional):**
```
## STYLE REFERENCE

The following claims from a similar patent should serve as a style guide.
Mimic the formatting, structure, and drafting conventions used in these
reference claims:

[Paste the reference patent's claims here]

When drafting claims for the disclosure, follow similar:
- Claim structure (preamble, transitional phrase, body with elements)
- Level of detail and specificity
- Dependent claim organization
- Technical language conventions
```

## Tips

- If you have a reference patent with claims in a similar technology area, include it as a style reference -- the LLM will match the drafting style and level of detail.
- After generating claims, run them through the [Detectability Assessment](../detectability-assessment/prompt.md) to evaluate enforcement feasibility.
- Consider generating claims in multiple forms: method claims, system claims, and computer-readable medium claims. You can run the prompt multiple times, changing the preamble direction each time.
- For software inventions, ensure the independent claim includes enough structure to satisfy 35 U.S.C. 101 -- pure abstract ideas without technical implementation will face eligibility rejections.
- Review dependent claims as potential fallback positions during prosecution. Each should add meaningful narrowing that distinguishes from likely prior art.

## Try It

Test this prompt using the sample data in [`../../examples/sample-disclosure.md`](../../examples/sample-disclosure.md).
