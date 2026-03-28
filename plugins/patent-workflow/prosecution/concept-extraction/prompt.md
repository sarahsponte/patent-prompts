# Patent Concept Extraction

> **Category**: Prosecution

## What This Does

Extracts the core patent concepts from a set of patent claims -- identifying the inventive technical approaches that make the innovation non-obvious, not just restating claim language or listing product features.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-concept-extraction.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# PATENT CONCEPT EXTRACTION FROM CLAIMS

You are a senior patent strategist and IP analyst conducting a comprehensive patent concept analysis. Your task is to identify and extract all relevant **Patent Concepts** from the patent claims below.

These concepts will serve as the foundation for:
- Prior art analysis and patent landscape mapping
- Patent claim drafting and continuation planning
- IP strategy development and portfolio optimization
- Patent-to-product feature mapping and claim chart preparation
- Licensing strategy and patent valuation assessments
- Patent prosecution support and amendment strategies

## PATENT CLAIMS TO ANALYZE

**Title:** {{PATENT_TITLE}}

**Claims:**
{{PATENT_CLAIMS}}

## PATENT CONCEPT DEFINITION FRAMEWORK

### What a Patent Concept IS:
- **Abstraction of the inventive idea** captured in the patent application or grant
- **Centered on the novel technical approach** that makes the invention non-obvious, not on business goals or branding
- **Derived from technical specifications** including patent claims
- **Implementation-oriented but broader than claim language** so it survives amendments and captures the core inventive step
- **Technically meaningful and defensible** -- defines what makes the invention distinguishable from prior art
- **IP strategy focused** -- used for prior-art analysis, claim drafting, continuation planning, and mapping patents to product features
- **Inventive step abstraction** that answers "what novel technical approach makes this invention possible?"

### What a Patent Concept is NOT:
- Not a verbatim claim or isolated claim limitation from the patent claims
- Not a product concept or marketing feature focused on customer benefits
- Not tied to a single implementation detail unless that detail is the core invention
- Not a generic statement like "improves performance" without describing the technical approach
- Not so broad that it becomes indistinguishable from prior art (e.g., "uses AI to optimize systems")
- Not business-oriented value propositions or user-facing benefits

### Key Distinction:
- **Product Concept**: "What value does the product provide to users?"
- **Patent Concept**: "What inventive technical approach makes this innovation possible?"

## ANALYSIS METHODOLOGY

1. **Deep Technical Analysis**: Thoroughly analyze the patent claims to understand the core inventions
2. **Inventive Step Mapping**: Identify the core technical approaches that distinguish this patent from prior art
3. **Technical Innovation Abstraction**: Extract novel technical methods, systems, and processes that represent the inventive contribution
4. **Patent Strategy Perspective**: Consider how these concepts would be used for claim drafting, prior art analysis, and patent prosecution
5. **Gap Analysis**: Ensure all major inventive technical approaches described in the claims are captured

## CONCEPT EXTRACTION CRITERIA

Each Patent Concept must:
- Represent a distinct inventive technical approach or novel method described in the patent claims
- Focus on technical innovation and novel implementation approaches
- Be broader than specific claim language but technically specific enough for IP analysis
- Remain meaningful for patent prosecution, prior art analysis, and claim mapping activities
- Focus on "how" the technical innovation works, not "what" user benefits it provides

## OUTPUT FORMAT

For each concept, provide:

### Concept [Number]: [Concept Name]

**Description:** [Detailed technical explanation of the novel method, system, or approach this concept represents]

**Supporting Claims:** [List the claim numbers that support this concept]

---

Provide a comprehensive list of all patent concepts. Aim for complete coverage of the inventive technical approaches while avoiding redundancy or overly broad generalizations. Typically expect 3-8 concepts depending on the breadth of the patent claims.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_TITLE}}` | The title of the patent or application |
| `{{PATENT_CLAIMS}}` | The full text of the patent claims (all claims, or at minimum all independent claims plus key dependent claims) |

## Tips

- Including dependent claims alongside independent claims produces better results -- dependent claims often contain the most technically specific inventive details.
- If you have the patent specification available, you can append it after the claims for richer concept extraction, though claims alone are sufficient.
- The output concepts are ideal starting points for prior art searches, claim charts, and continuation planning.
- Run the extraction on multiple related patents in a family to identify gaps in concept coverage across the portfolio.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
