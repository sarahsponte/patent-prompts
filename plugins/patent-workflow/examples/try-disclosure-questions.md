# Try It: Disclosure Questions

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample disclosure](sample-disclosure.md) included in this repo.

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

Context-Aware Emergency Vehicle Preemption System for Connected Intersections

### Description

This invention provides an intelligent traffic signal preemption system that dynamically clears a path for emergency vehicles through connected intersections using vehicle-to-infrastructure (V2I) communication and predictive route modeling.

The system installs a V2I communication receiver at each equipped intersection that listens for standardized priority request messages broadcast by emergency vehicles. When a priority request message is received, the system determines the emergency vehicle's current GPS position, heading, and speed, and computes an estimated time of arrival (ETA) at the intersection.

Unlike conventional preemption systems that simply force a green signal when an emergency vehicle is detected within a fixed range, this system incorporates a context-aware preemption engine. The preemption engine evaluates the current traffic state at the intersection -- including the active signal phase, the number of vehicles queued in each lane (estimated from existing loop detectors or imaging sensors), and the pedestrian density in any active crosswalk -- before determining the optimal preemption strategy.

The preemption engine selects from a library of preemption strategies based on the computed ETA and the current intersection state. Strategies include: (a) early green termination for conflicting phases, (b) phase insertion where a dedicated emergency green phase is injected into the signal cycle, (c) pedestrian flush where the pedestrian crossing interval is accelerated to clear pedestrians before the emergency vehicle arrives, and (d) queue discharge where a brief green is given to the queued direction to clear vehicles blocking the emergency vehicle's path before switching to the emergency phase.

A predictive route model estimates the emergency vehicle's most likely route through a corridor of intersections and sends advance preemption preparation commands to downstream intersections. This enables a cascading preemption wave where each intersection begins clearing traffic before the emergency vehicle arrives, reducing total corridor transit time.

After the emergency vehicle passes, the system executes a recovery sequence that returns the intersection to its normal signal timing plan with minimal disruption. The recovery sequence uses a graduated transition that prioritizes the directions with the longest accumulated queue to prevent secondary congestion.

### Key Difference

While the sample patent (Adaptive Traffic Signal Control System Using Real-Time Pedestrian Detection) focuses on adjusting normal signal timing based on pedestrian density and predictive queue modeling for everyday operation, this invention addresses the distinct problem of emergency vehicle preemption. The core innovation is the **context-aware preemption engine** that selects among multiple preemption strategies based on the real-time intersection state -- including pedestrian presence, queue lengths, and active signal phase -- rather than applying a one-size-fits-all forced green. The predictive route model enabling cascading preemption across a corridor of intersections is also novel.

This system could complement the pedestrian detection system described in the sample patent: the pedestrian density value from that system could serve as an input to this system's preemption engine, informing the pedestrian flush strategy decision. However, the inventive concepts -- V2I-based preemption triggering, multi-strategy preemption selection, corridor-level cascading preemption, and graduated recovery sequencing -- are distinct from pedestrian detection and adaptive timing.

### Supporting Documents

- The V2I communication follows the SAE J2735 standard for priority request messages (Signal Request Message / Signal Status Message).
- The preemption strategy library is extensible; additional strategies can be added without modifying the core preemption engine.
- The system logs all preemption events, including the selected strategy, ETA accuracy, and recovery time, for post-incident analysis and system tuning.
- Initial testing was conducted in simulation using SUMO (Simulation of Urban Mobility) with a 12-intersection corridor model, showing a 34% reduction in emergency vehicle corridor transit time compared to conventional preemption.

## YOUR TASK

Generate exactly 10 strategic questions based on the disclosure materials above. Each question should reference specific technical details from the disclosure and serve a clear patent strategy purpose.
