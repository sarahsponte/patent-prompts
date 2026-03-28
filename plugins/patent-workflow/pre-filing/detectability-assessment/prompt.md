# Detectability Assessment

> **Category**: Pre-Filing

## What This Does

Evaluates how easily an invention's implementation can be detected in potentially infringing products, helping you decide whether to patent it and how to structure claims for maximum enforceability. Works for both pre-filing disclosures and issued patent claims.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-detectability-assessment.md) using our sample data and paste it directly into any LLM.

**Choose your input type:**
- For **pre-filing disclosures**: provide the invention title, description, and key difference
- For **issued patents**: provide the independent claims text instead

## The Prompt

---

# PATENT ENFORCEMENT STRATEGIC ASSESSMENT: DETECTABILITY ANALYSIS

You are a senior patent enforcement strategist and litigation advisor. Your task is to evaluate how easily the claimed subject matter can be detected in potentially infringing products or systems.

## MISSION

This analysis directly impacts:
- **Enforcement Feasibility**: Can infringement be proven without prohibitive costs?
- **Patent Portfolio Strategy**: Should this invention be prioritized for patent protection?
- **Claim Drafting Guidance**: How should claims be structured to maximize detectability?
- **Licensing Strategy**: Detectable patents command higher licensing value
- **Litigation Risk Assessment**: What level of evidence gathering would be required?

## DETECTABILITY FRAMEWORK

### HIGH DETECTABILITY
**Definition**: The claimed subject matter is visible in end products, user interfaces, or publicly accessible outputs.

**Characteristics**:
- Manifests in client-side code, UI elements, device outputs, or product specifications
- Observable through: product purchase, user testing, API inspection, reverse engineering, or public documentation
- Evidence obtainable without discovery or insider access
- Direct proof of implementation is readily available

**Examples**:
- UI layouts and interaction patterns visible to users
- Mechanical designs and product form factors
- Sensor arrangements and hardware configurations
- Published API specifications and protocols
- Client-side algorithms (JavaScript, mobile app logic)
- Device output characteristics (display behavior, audio patterns)
- File format structures
- Public-facing system behaviors

### MEDIUM DETECTABILITY
**Definition**: The claimed subject matter requires technical analysis but can be detected with reasonable effort and expense.

**Characteristics**:
- Not directly visible but inferable from performance, outputs, metadata, or partial reverse engineering
- Detectable through: network monitoring, performance benchmarking, metadata analysis, technical testing, or protocol analysis
- Some aspects publicly observable; full picture requires investigation
- Evidence gathering is feasible but requires technical expertise

**Examples**:
- Communication protocols and data transmission patterns
- Performance characteristics and timing behaviors
- Compression algorithm effects on outputs
- API response patterns and structures
- Caching mechanisms observable through behavior
- Error handling patterns
- Quality-of-service mechanisms
- Network traffic patterns

### LOW DETECTABILITY
**Definition**: The claimed subject matter is hidden in private systems, servers, or internal processes.

**Characteristics**:
- Manifests entirely server-side, in backend infrastructure, or during confidential manufacturing processes
- Requires: discovery process, insider testimony, subpoenaed documents, or access to confidential systems
- No external evidence trail available to third parties
- Detection would require litigation and formal discovery

**Examples**:
- Server-side algorithms and business logic
- Backend ranking and recommendation systems
- Internal database structures and optimization methods
- Manufacturing trade secrets and process details
- Internal data processing pipelines
- Cloud infrastructure implementations
- Proprietary quality scoring systems
- Backend security mechanisms

## ANALYSIS METHODOLOGY

Follow this systematic approach:

### Step 1: Identify the Core Novelty
Extract the core innovative aspect:
- What is the single most important novel element?
- What makes this invention unique and patentable?
- Is it a method, system, feature, process, or algorithm?

### Step 2: Determine Where It Manifests
Identify the primary manifestation point(s):
- **Client-side**: User interface, mobile app, browser, client software
- **Server-side**: Backend servers, cloud infrastructure, APIs
- **Network**: Communication protocols, data transmission
- **Manufacturing**: Production processes, fabrication methods
- **Output**: Product behavior, device outputs, generated data
- **Hybrid**: Multiple manifestation points (specify which aspects are where)

### Step 3: Assess Observable Characteristics
Evaluate what can be observed or measured externally:
- What evidence would be visible to a user or customer?
- What could be detected through reverse engineering?
- What could be inferred from product behavior or outputs?
- What technical analysis methods could reveal the claimed features?

### Step 4: Identify Required Detection Methods
Determine how infringement would be proven:
- **Direct observation**: Product purchase, user testing, visual inspection
- **Technical analysis**: Reverse engineering, network monitoring, performance testing
- **Public documentation**: Manuals, specifications, patents, marketing materials
- **Discovery process**: Subpoenas, depositions, source code review, expert testimony

### Step 5: Evaluate Barriers to Detection
Identify obstacles to proving infringement:
- Encryption or obfuscation techniques
- Server-side implementation (no client access)
- Proprietary or closed systems
- Manufacturing confidentiality
- Complex multi-component systems
- Cloud deployment (infrastructure not accessible)

## SUBJECT MATTER TO ANALYZE

{{PATENT_CLAIMS}}

## OUTPUT FORMAT

Structure your response in markdown with the following sections:

### Detectability Rating

State the overall rating: **HIGH**, **MEDIUM**, or **LOW**

### Detection Analysis

Cover these areas with bullet points:
- **Most Difficult to Detect Element**: Identify the specific aspect that would be the most challenging to detect in practice
- **Required Detection Methods**: Specific approaches needed to prove infringement. For each method, estimate the approximate cost and time required (e.g., "product purchase + teardown, ~$500, 1-2 weeks" or "network traffic analysis, ~$2,000, 2-4 weeks")
- **Barriers to Detection**: What makes detection difficult or impossible without discovery
- **Detectability Assessment**: Clear rationale for the assigned detectability level
- **Adversarial Assessment**: Identify the single claim element an accused infringer would most strongly argue is undetectable, and evaluate whether they are right

### Evidence Availability

Provide two subsections:
- **Directly Accessible Evidence**: List specific types of evidence obtainable without litigation, explain how each type of evidence would reveal the claimed features, include feasibility and cost considerations
- **Discovery-Required Evidence**: List specific types of evidence requiring formal discovery, explain why discovery is necessary for each, note the litigation implications

### Element Detectability Matrix

| Claim Element | Where It Manifests | Detection Method | Cost/Time Estimate | Detectability |
|---|---|---|---|---|
| [element text] | [client/server/network/etc.] | [specific method] | [estimate] | HIGH / MEDIUM / LOW |

## CRITICAL GUIDANCE

**Be Strategic**: Frame your analysis from an enforcement feasibility perspective -- focus on whether infringement can actually be proven, not just whether the invention is technically detectable in theory.

**Be Specific**: Provide concrete, actionable assessment. Avoid generic statements. Explain exactly where the claimed subject matter manifests and what evidence would be available.

**Be Realistic**: Consider practical enforcement scenarios. Would a company actually be able to prove infringement without prohibitive costs?

**Be Clear**: Use plain language that can be understood and acted upon. This analysis drives business decisions about patent strategy.

Begin your comprehensive detectability analysis now.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_CLAIMS}}` | The subject matter to analyze. Use **one** of the following formats: |

**Option A -- For pre-filing disclosures:**
```
**Title**: [invention title]

**Description**:
[full invention description]

**Key Difference**:
[what makes this different from existing solutions]
```

**Option B -- For issued patents or drafted claims:**
```
Claim 1. [full text of independent claim 1]

Claim X. [full text of independent claim X]

[Include all independent claims]
```

## Tips

- For pre-filing assessments, use the results to guide how you draft claims -- push detectable elements into independent claims and keep hard-to-detect elements in dependent claims.
- If the assessment comes back as LOW detectability, consider whether the claims can be restructured to capture externally observable aspects of the invention.
- Run this assessment on competitor patents too -- low detectability patents from competitors may be less of a litigation threat.
- Pair this with the [Claims Drafting](../../pre-filing/claims-drafting/prompt.md) prompt to draft claims optimized for detectability.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md) or [`../../examples/sample-disclosure.md`](../../examples/sample-disclosure.md).
