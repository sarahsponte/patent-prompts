# Try It: Patent Concept Extraction

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

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

**Title:** Adaptive Traffic Signal Control System Using Real-Time Pedestrian Detection

**Claims:**
### Independent Claim 1 (Method)

1. A method for controlling traffic signals at an intersection, the method comprising:
   - capturing, by a plurality of imaging sensors positioned at the intersection, a sequence of image frames of at least one crosswalk area;
   - processing, by a pedestrian detection module, each image frame through a multi-stage classification pipeline, the multi-stage classification pipeline comprising:
     - a motion segmentation stage that isolates moving objects from a background model to produce a set of motion regions;
     - a candidate region generator that identifies, from the set of motion regions, regions of interest containing potential pedestrians; and
     - a shape classification stage that applies a trained discriminative model to each region of interest to generate a pedestrian confidence score;
   - determining, by the pedestrian detection module, a pedestrian density value for the at least one crosswalk area based on the pedestrian confidence scores exceeding a configurable detection threshold;
   - generating, by a predictive queue model, an estimated future pedestrian arrival rate based on the pedestrian density value and historical pedestrian traffic patterns stored in a pattern database; and
   - adjusting, by a signal timing controller, at least one of a green phase duration and a pedestrian crossing interval based on the pedestrian density value and the estimated future pedestrian arrival rate.

**Dependent Claims:**

2. The method of claim 1, wherein the motion segmentation stage updates the background model using an adaptive learning rate that increases during periods of low traffic activity and decreases during periods of high traffic activity.

3. The method of claim 1, wherein the trained discriminative model comprises a histogram of oriented gradients feature extractor coupled with a support vector machine classifier.

4. The method of claim 1, further comprising transmitting, by the signal timing controller, the adjusted green phase duration to an adjacent intersection controller via a dedicated communication link to coordinate signal timing across a plurality of intersections.

### Independent Claim 5 (System)

5. A traffic signal control system comprising:
   - a plurality of imaging sensors positioned at an intersection and configured to capture a sequence of image frames of at least one crosswalk area;
   - a processor; and
   - a memory storing instructions that, when executed by the processor, cause the processor to:
     - process each image frame through a multi-stage classification pipeline comprising a motion segmentation stage, a candidate region generator, and a shape classification stage that applies a trained discriminative model to generate a pedestrian confidence score for each region of interest;
     - determine a pedestrian density value for the at least one crosswalk area based on pedestrian confidence scores exceeding a configurable detection threshold;
     - generate, using a predictive queue model, an estimated future pedestrian arrival rate based on the pedestrian density value and historical pedestrian traffic patterns; and
     - adjust at least one of a green phase duration and a pedestrian crossing interval based on the pedestrian density value and the estimated future pedestrian arrival rate.

**Dependent Claims:**

6. The system of claim 5, wherein the plurality of imaging sensors comprises at least one infrared sensor and at least one visible-light camera, and wherein the pedestrian detection module fuses data from the infrared sensor and the visible-light camera to improve detection accuracy in low-light conditions.

7. The system of claim 5, wherein the configurable detection threshold is dynamically adjusted based on ambient lighting conditions measured by a photometric sensor.

8. The system of claim 5, further comprising a display unit configured to present the pedestrian density value and signal timing parameters to a traffic management operator in real time.

### Independent Claim 9 (Computer-Readable Medium)

9. A non-transitory computer-readable medium storing instructions that, when executed by a processor, cause the processor to perform operations comprising:
   - receiving a sequence of image frames from a plurality of imaging sensors positioned at an intersection;
   - processing each image frame through a multi-stage classification pipeline to detect pedestrians in at least one crosswalk area, the multi-stage classification pipeline comprising a motion segmentation stage that isolates moving objects from a background model, a candidate region generator, and a shape classification stage;
   - determining a pedestrian density value based on detected pedestrians exceeding a configurable detection threshold;
   - generating an estimated future pedestrian arrival rate using a predictive queue model that analyzes the pedestrian density value and historical pedestrian traffic patterns; and
   - outputting signal timing adjustment data comprising at least one of an adjusted green phase duration and an adjusted pedestrian crossing interval.

**Dependent Claims:**

10. The non-transitory computer-readable medium of claim 9, wherein the operations further comprise logging the pedestrian density value and the signal timing adjustment data to an audit database for subsequent performance analysis.

11. The non-transitory computer-readable medium of claim 9, wherein the predictive queue model applies a weighted moving average to the historical pedestrian traffic patterns, with more recent patterns receiving a higher weight.

12. The non-transitory computer-readable medium of claim 9, wherein the operations further comprise detecting a pedestrian group comprising three or more pedestrians within a defined spatial proximity and extending the pedestrian crossing interval by a group accommodation factor.

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
