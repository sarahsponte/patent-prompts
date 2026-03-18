# Try It: Claims Drafting

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample disclosure](sample-disclosure.md) included in this repo.

---

# PATENT CLAIMS DRAFTING

You are a senior patent attorney drafting patent claims for a new invention disclosure. Your task is to generate well-structured patent claims that capture the novel aspects of the invention.

## DISCLOSURE MATERIALS

**Title:** Context-Aware Emergency Vehicle Preemption System for Connected Intersections

**Description:**

This invention provides an intelligent traffic signal preemption system that dynamically clears a path for emergency vehicles through connected intersections using vehicle-to-infrastructure (V2I) communication and predictive route modeling.

The system installs a V2I communication receiver at each equipped intersection that listens for standardized priority request messages broadcast by emergency vehicles. When a priority request message is received, the system determines the emergency vehicle's current GPS position, heading, and speed, and computes an estimated time of arrival (ETA) at the intersection.

Unlike conventional preemption systems that simply force a green signal when an emergency vehicle is detected within a fixed range, this system incorporates a context-aware preemption engine. The preemption engine evaluates the current traffic state at the intersection -- including the active signal phase, the number of vehicles queued in each lane (estimated from existing loop detectors or imaging sensors), and the pedestrian density in any active crosswalk -- before determining the optimal preemption strategy.

The preemption engine selects from a library of preemption strategies based on the computed ETA and the current intersection state. Strategies include: (a) early green termination for conflicting phases, (b) phase insertion where a dedicated emergency green phase is injected into the signal cycle, (c) pedestrian flush where the pedestrian crossing interval is accelerated to clear pedestrians before the emergency vehicle arrives, and (d) queue discharge where a brief green is given to the queued direction to clear vehicles blocking the emergency vehicle's path before switching to the emergency phase.

A predictive route model estimates the emergency vehicle's most likely route through a corridor of intersections and sends advance preemption preparation commands to downstream intersections. This enables a cascading preemption wave where each intersection begins clearing traffic before the emergency vehicle arrives, reducing total corridor transit time.

After the emergency vehicle passes, the system executes a recovery sequence that returns the intersection to its normal signal timing plan with minimal disruption. The recovery sequence uses a graduated transition that prioritizes the directions with the longest accumulated queue to prevent secondary congestion.

**Key Difference/Innovation:**

While the sample patent (Adaptive Traffic Signal Control System Using Real-Time Pedestrian Detection) focuses on adjusting normal signal timing based on pedestrian density and predictive queue modeling for everyday operation, this invention addresses the distinct problem of emergency vehicle preemption. The core innovation is the **context-aware preemption engine** that selects among multiple preemption strategies based on the real-time intersection state -- including pedestrian presence, queue lengths, and active signal phase -- rather than applying a one-size-fits-all forced green. The predictive route model enabling cascading preemption across a corridor of intersections is also novel.

This system could complement the pedestrian detection system described in the sample patent: the pedestrian density value from that system could serve as an input to this system's preemption engine, informing the pedestrian flush strategy decision. However, the inventive concepts -- V2I-based preemption triggering, multi-strategy preemption selection, corridor-level cascading preemption, and graduated recovery sequencing -- are distinct from pedestrian detection and adaptive timing.

**Supporting Documents:**

- The V2I communication follows the SAE J2735 standard for priority request messages (Signal Request Message / Signal Status Message).
- The preemption strategy library is extensible; additional strategies can be added without modifying the core preemption engine.
- The system logs all preemption events, including the selected strategy, ETA accuracy, and recovery time, for post-incident analysis and system tuning.
- Initial testing was conducted in simulation using SUMO (Simulation of Urban Mobility) with a 12-intersection corridor model, showing a 34% reduction in emergency vehicle corridor transit time compared to conventional preemption.

## TASK

Analyze the disclosure materials and draft patent claims that capture the **broadest defensible scope** of the invention.

### Claim Scope Strategy

**CRITICAL: Draft the BROADEST defensible claim, not a narrow implementation.**

- Use functional language ("configured to", "operable to") over structural limitations
- Focus on HOW the invention works, not just WHAT it achieves
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
