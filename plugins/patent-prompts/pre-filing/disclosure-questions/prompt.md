# Disclosure Questions

> **Category**: Pre-Filing

## What This Does

Generates 10 strategic questions for enriching an invention disclosure before patent drafting. Questions span technical clarification, inventive insight extraction, claim strategy, alternative embodiments, and commercial context -- prioritized by impact on patent strength.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-disclosure-questions.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

# PATENT DISCLOSURE ENRICHMENT: STRATEGIC QUESTION GENERATION

You are an expert patent strategist and drafting specialist. Your task is to generate strategic questions that will be used when preparing invention disclosures with inventors before forwarding to outside counsel for patent drafting.

## MISSION

Generate exactly 10 deep, strategic, and technically grounded questions that will:

- **Enrich Technical Details**: Elicit underlying algorithms, control logic, materials, sensors, interactions, and implementation specifics
- **Broaden Claim Scope**: Identify alternative embodiments and approaches that competitors might use
- **Strengthen Commercial Value**: Connect the invention to industry problems, product roadmap, and competitive landscape
- **Support Claim Drafting**: Surface distinctions from prior art and functional claim opportunities
- **Extract Inventive Insights**: Reveal non-obvious aspects, unexpected results, and key design trade-offs

## QUESTION GENERATION FRAMEWORK

Your questions should span these five strategic areas, listed in order of priority for patent strength:

### 1. Technical Clarification Questions (HIGHEST PRIORITY)

Focus on gaps in technical disclosure that affect claim strength:
- Underlying algorithms, data structures, or computational methods
- Control logic, decision trees, or state machines
- Materials, sensors, hardware components, or physical arrangements
- System interactions, interfaces, or integration points
- Implementation details that distinguish from obvious approaches

Ask "how" and "why" questions that expose inventive rationales. Probe aspects that could make the invention easier or harder for competitors to design around.

### 2. Inventive Insight Extraction (HIGHEST PRIORITY)

Surface non-obviousness and unexpected advantages:
- "What surprised you during development?"
- "What was unexpectedly difficult or required creative problem-solving?"
- "What trade-offs did you evaluate, and why did you choose this approach?"
- "What results were better than expected, or different from prior solutions?"
- "What technical barriers did this overcome that others haven't solved?"

Ask questions that reveal the inventor's creative journey and decision-making process. These insights directly support non-obviousness arguments.

### 3. Claim Strategy Development (HIGH PRIORITY)

Focus on patentability and claim construction:
- What distinguishes this invention from prior art or existing solutions
- Functional claim opportunities (method, apparatus, system, computer-readable medium)
- Independent claim scope vs. dependent claim specifics
- Fallback embodiments for continuation or divisional filings
- Claim elements that maximize enforceability and detectability

Ask about the "inventive core" that should anchor independent claims.

### 4. Alternative Embodiments & Competitive Coverage (MEDIUM PRIORITY)

Explore variations that achieve similar results:
- Alternative architectures, configurations, or system designs
- Different materials, components, or manufacturing methods
- Software vs. firmware vs. hardware implementations
- AI-driven vs. rule-based approaches
- Configurations competitors might use to achieve the same function

Ask whether similar results could be achieved through different means, and whether those alternatives could be captured in claims.

### 5. Commercial & Industry Context (LOWER PRIORITY)

Connect the invention to business value and market positioning:
- How the invention fits within the company's product roadmap
- Specific industry problems solved or gaps competitors cannot fill
- Integration with existing standards, platforms, or ecosystems
- Market differentiators and competitive advantages
- Customer pain points addressed by the invention

Ask questions that elicit concrete examples of commercial applications and competitive scenarios.

## OUTPUT REQUIREMENTS

Generate exactly 10 questions. For each question, include:

1. The question text
2. Category (one of: Technical Clarification, Inventive Insight, Claim Strategy, Alternative Embodiments, Commercial Context)
3. Priority score (1-10, where 1 = most critical) based on how essential the answer is for drafting a strong patent. Use these guidelines:
   - **1-3 (Critical)**: Questions addressing fundamental gaps in Technical Clarification or Inventive Insight that would significantly weaken the patent if unanswered
   - **4-5 (High)**: Questions about Claim Strategy or critical alternative embodiments
   - **6-7 (Medium)**: Questions about Alternative Embodiments and competitive coverage
   - **8-10 (Lower)**: Questions about Commercial Context or supplementary details

Format your output as a numbered list. For each question, use this format:

**[Number]. [Question text]**
- **Category**: [category name]
- **Priority**: [score]/10

Each question must:

1. **Reference Specific Disclosure Details**: Use concrete technical hooks from the disclosure materials (e.g., if the disclosure mentions "gesture-based AR control," ask about the gesture recognition pipeline, latency requirements, sensor fusion methods, etc.)

2. **Be Strategically Focused**: Each question should serve a clear patent strategy purpose -- technical depth, claim breadth, competitive coverage, or non-obviousness

3. **Be Actionable**: Questions should elicit specific, concrete information that outside counsel can use when drafting patent applications

4. **Be Inventor-Friendly**: Frame questions in a way that makes inventors feel understood and engaged, not interrogated

## CRITICAL GUIDANCE

**Prioritize Technical Clarification and Inventive Insights**: At least 4-5 questions should fall into these two highest-priority categories. These questions directly impact claim strength and non-obviousness arguments.

**Be Specific**: Avoid generic questions like "How does the system work?" Instead, reference specific technical elements from the disclosure.

**Be Strategic**: Focus on what matters for patent value -- claim scope, competitive coverage, enforceability, and non-obviousness.

**Be Practical**: Frame questions that inventors can answer concretely, not abstract theoretical questions.

## DISCLOSURE MATERIALS

### Title

{{INVENTION_TITLE}}

### Description

{{INVENTION_DESCRIPTION}}

### Key Difference

{{KEY_DIFFERENCE}}

### Supporting Documents

{{SUPPORTING_DOCUMENTS}}

## YOUR TASK

Generate exactly 10 strategic questions based on the disclosure materials above. Each question should reference specific technical details from the disclosure and serve a clear patent strategy purpose.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{INVENTION_TITLE}}` | Title of the invention disclosure |
| `{{INVENTION_DESCRIPTION}}` | Full description of the invention -- what it does, how it works, what problem it solves |
| `{{KEY_DIFFERENCE}}` | What makes this invention different from existing solutions or prior art |
| `{{SUPPORTING_DOCUMENTS}}` | Any additional materials -- diagrams, technical specs, whiteboard photos, etc. Write "None" if not available |

## Tips

- The more detail you provide in the description and key difference fields, the more targeted and useful the questions will be.
- If you have technical diagrams or flowcharts, describe them in the supporting documents section -- this helps generate questions about system architecture and data flow.
- Use the priority scores to decide which questions to ask first if inventor time is limited.
- After getting answers, you can run this prompt again with the enriched disclosure to generate a second round of deeper questions.

## Try It

Test this prompt using the sample data in [`../../examples/sample-disclosure.md`](../../examples/sample-disclosure.md).
