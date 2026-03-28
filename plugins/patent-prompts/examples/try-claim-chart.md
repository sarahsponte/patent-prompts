# Try It: Claim Chart Generation

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

You are a patent litigation analyst preparing a claim chart. Your task is to map each element of the provided patent claims against the described product, determining whether each element is practiced by the product.

**Your guiding principle is accuracy over coverage.** One honest "not covered" finding is worth more than ten speculative "covered" findings. Never stretch evidence to find infringement where it does not clearly exist.

## Independent Claims

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

### Independent Claim 5 (System)

5. A traffic signal control system comprising:
   - a plurality of imaging sensors positioned at an intersection and configured to capture a sequence of image frames of at least one crosswalk area;
   - a processor; and
   - a memory storing instructions that, when executed by the processor, cause the processor to:
     - process each image frame through a multi-stage classification pipeline comprising a motion segmentation stage, a candidate region generator, and a shape classification stage that applies a trained discriminative model to generate a pedestrian confidence score for each region of interest;
     - determine a pedestrian density value for the at least one crosswalk area based on pedestrian confidence scores exceeding a configurable detection threshold;
     - generate, using a predictive queue model, an estimated future pedestrian arrival rate based on the pedestrian density value and historical pedestrian traffic patterns; and
     - adjust at least one of a green phase duration and a pedestrian crossing interval based on the pedestrian density value and the estimated future pedestrian arrival rate.

### Independent Claim 9 (Computer-Readable Medium)

9. A non-transitory computer-readable medium storing instructions that, when executed by a processor, cause the processor to perform operations comprising:
   - receiving a sequence of image frames from a plurality of imaging sensors positioned at an intersection;
   - processing each image frame through a multi-stage classification pipeline to detect pedestrians in at least one crosswalk area, the multi-stage classification pipeline comprising a motion segmentation stage that isolates moving objects from a background model, a candidate region generator, and a shape classification stage;
   - determining a pedestrian density value based on detected pedestrians exceeding a configurable detection threshold;
   - generating an estimated future pedestrian arrival rate using a predictive queue model that analyzes the pedestrian density value and historical pedestrian traffic patterns; and
   - outputting signal timing adjustment data comprising at least one of an adjusted green phase duration and an adjusted pedestrian crossing interval.

## Product Description

SmartCross Pedestrian Safety Platform (CityFlow Technologies)

The SmartCross system is a computer vision-based pedestrian safety platform deployed at urban intersections. The system uses pole-mounted cameras to monitor crosswalk areas in real time.

Key features:
- Dual-sensor approach combining thermal imaging cameras and standard HD cameras for all-weather pedestrian detection
- AI-powered detection pipeline that first identifies motion zones in the camera feed, then isolates candidate pedestrian regions based on size filtering, then runs each candidate through a deep learning classifier to confirm pedestrian presence
- Real-time pedestrian counting that estimates how many people are waiting at or crossing each crosswalk
- Historical pattern analysis that uses past pedestrian traffic data to predict when crosswalks will be busy, enabling preemptive signal adjustments
- Automatic signal timing modification that extends walk signals when high pedestrian volumes are detected and shortens them during low-traffic periods
- Group detection feature that identifies clusters of 3+ pedestrians and automatically adds extra crossing time
- Inter-intersection communication module that shares signal timing data with neighboring intersections to create coordinated pedestrian corridors
- Dashboard for traffic operators showing live pedestrian counts and signal status

## Web Search Results

### Search 1: "SmartCross CityFlow Technologies pedestrian detection system"

**CityFlow Technologies — SmartCross Product Page**
SmartCross is an AI-powered pedestrian safety platform for urban intersections. The system uses pole-mounted dual-sensor units (thermal + HD visible-light cameras) to detect and count pedestrians at crosswalks in real time. SmartCross integrates directly with existing traffic signal controllers via NTCIP protocol. Deployed in 45+ cities across North America. Each intersection unit includes an edge computing module running the CityFlow PedSense detection engine.

**CityFlow Technologies — SmartCross Technical Datasheet (PDF excerpt)**
Detection Pipeline: SmartCross PedSense v3.2 uses a three-stage detection architecture: (1) frame differencing against an adaptive background model to identify motion regions, (2) spatial filtering to extract candidate pedestrian regions based on calibrated size thresholds, (3) a convolutional neural network (CNN) classifier that assigns a detection confidence score to each candidate. Minimum confidence threshold is operator-configurable (default 0.85). System outputs a per-crosswalk pedestrian count updated every 500ms.

### Search 2: "SmartCross predictive signal timing pedestrian"

**CityFlow Blog — "Introducing Predictive Timing in SmartCross v4.0" (March 2024)**
SmartCross v4.0 adds predictive signal timing capabilities. The system now analyzes historical pedestrian volume data (stored per-intersection in a local database) alongside real-time counts to forecast near-term pedestrian demand. When predicted demand exceeds a threshold, the system preemptively extends pedestrian phases before congestion builds. Early deployments show a 23% reduction in average pedestrian wait time.

**Smart Cities World — "CityFlow Deploys Predictive Pedestrian System in Austin" (June 2024)**
CityFlow Technologies has deployed its SmartCross system with predictive timing at 12 intersections in downtown Austin. The system uses past pedestrian traffic patterns to anticipate peak crosswalk usage and adjust signal timing proactively. The Austin deployment also uses SmartCross's intersection-to-intersection communication feature to coordinate walk signals along Congress Avenue, creating a "pedestrian green wave."

## Patent Specification (Optional)

The present invention relates to an adaptive traffic signal control system that dynamically adjusts signal timing at intersections based on real-time pedestrian detection and density estimation.

**Pedestrian Detection Module.** The pedestrian detection module 140 processes each captured image frame through a multi-stage classification pipeline 200. The multi-stage classification pipeline 200 comprises three sequential stages. The first stage is a motion segmentation stage 210 that isolates moving objects from a background model 215. The motion segmentation stage 210 produces a set of motion regions 220 representing areas of the image frame where movement has been detected. The second stage is a candidate region generator 230 that identifies, from the set of motion regions 220, regions of interest 235 containing potential pedestrians. The candidate region generator 230 applies spatial filtering to exclude regions that are too small or too large to represent a human figure. The third stage is a shape classification stage 240 that applies a trained discriminative model 245 to each region of interest 235 to generate a pedestrian confidence score 250. In one embodiment, the trained discriminative model 245 comprises a histogram of oriented gradients (HOG) feature extractor coupled with a support vector machine (SVM) classifier. The pedestrian detection module 140 determines a pedestrian density value 260 by counting the number of regions of interest 235 having a pedestrian confidence score 250 exceeding a configurable detection threshold 255.

**Predictive Queue Model.** The predictive queue model 150 generates an estimated future pedestrian arrival rate 310 based on the current pedestrian density value 260 and historical pedestrian traffic patterns 320 stored in a pattern database 155. The predictive queue model 150 applies a weighted moving average to the historical pedestrian traffic patterns 320, with more recent patterns receiving a higher weight. The estimated future pedestrian arrival rate 310 enables the system to proactively adjust signal timing before pedestrian congestion occurs.

**Signal Timing Controller.** The signal timing controller 160 adjusts at least one of a green phase duration 410 and a pedestrian crossing interval 420 based on the pedestrian density value 260 and the estimated future pedestrian arrival rate 310.

## Prosecution History (Optional)

No prosecution history available for this example.

## Claim Construction Framework

Construe each claim term using its **ordinary and customary meaning** as understood by a person of ordinary skill in the art at the time of the invention. Where the claim language is clear, apply it as written. Where ambiguous, consider:
- The claim language itself (intrinsic evidence, highest priority)
- How the term is used across all claims (claim differentiation)
- The specification as a dictionary for claim terms, if provided
- The prosecution history, if provided

Do not import limitations from the specification into the claims unless the patentee clearly acted as their own lexicographer or explicitly disclaimed scope.

## Infringement Analysis Framework

Analyze each claim element under the following three theories, in order of strength:

### 1. Direct Infringement (35 U.S.C. 271(a)) - Literal Infringement

- Does the product literally practice this claim element?
- Is there a one-to-one correspondence between the claim limitation and a product feature?
- Literal infringement requires that **every element** of the claim is present in the accused product.
- Provide specific evidence from the product description showing the product meets the limitation.

### 2. Indirect Infringement (35 U.S.C. 271(b)) - Induced Infringement

- Does the product maker actively induce others to infringe?
- Is there evidence of encouraging, instructing, or aiding others to use the product in an infringing manner?
- Consider product instructions, documentation, marketing materials, and intended use.

### 3. Doctrine of Equivalents (DoE)

If not literal infringement, does the product feature perform:
- **Substantially the same function**, in
- **Substantially the same way**, to achieve
- **Substantially the same result** as the claimed element?

**Critical DoE constraints:**
- DoE requires evidence of the ACTUAL mechanism used by the product. You cannot apply DoE if you only know the product achieves a similar result but not HOW it achieves it.
- "We don't know the mechanism but the result is similar" is NOT sufficient for DoE.
- DoE cannot be used to fill gaps in evidence. If you lack evidence of the product's internal mechanism, the element is NOT covered under DoE.

## Anti-Speculation Rules

Before marking ANY element as covered, verify all of the following:

1. **No fabrication**: Every factual assertion about the product must trace directly to the provided product description. Do not invent or assume product features not described.

2. **Mechanism vs. outcome**: Your evidence must show the product uses the specific MECHANISM described in the claim element, not merely that the product achieves a similar outcome or result. If you only have evidence of what the product does (outcome) but not how it does it (mechanism), the element is NOT covered.

3. **No speculative language**: If your analysis contains any of these phrases, the element is likely NOT covered: "likely", "probably", "presumably", "consistent with", "suggests", "would be expected to", "appears to", "mirrors", "if present". Rewrite to remove speculation or mark the element as not covered.

4. **No self-contradiction**: If your analysis acknowledges missing evidence anywhere (e.g., "not explicitly confirmed", "no documentation of", "while not described"), the element is NOT covered. Do not acknowledge a gap and then conclude coverage anyway.

5. **No claim paraphrasing as evidence**: Your evidence must come from the product description, not be a restatement of what the claim requires. If your evidence paragraph reads like a rephrasing of the claim element, you are paraphrasing, not providing evidence.

6. **Logical consistency**: Your coverage determination for each element must be logically consistent with your analysis. If your analysis identifies gaps or uncertainties, your determination must reflect that.

## Analysis Instructions

1. **Parse claims into elements**: Break each claim into its constituent elements (preamble, body elements, whereby clauses, etc.).

2. **Construe claim terms**: Apply the claim construction framework above to interpret key terms before mapping to the product.

3. **Map element by element**: For each claim element, identify the corresponding product feature from the product description and analyze under the infringement frameworks.

4. **Apply anti-speculation rules**: Before finalizing each element's coverage determination, run through all six anti-speculation checks.

5. **Determine overall claim coverage**: A claim is only fully covered if ALL elements are covered. Partial coverage should be noted but does not constitute infringement.

6. **Final cross-check**: For each element marked as "covered," re-read your analysis and confirm: (a) your evidence comes from the product description, not a restatement of the claim, (b) you identified the specific mechanism, not just a similar outcome, and (c) no speculative language remains.

## Output Format

For each independent claim (and its dependent claims), provide:

### Claim [Number] - [Covered / Partially Covered / Not Covered]

| # | Claim Element | Product Feature | Analysis | Infringement Theory | Covered? |
|---|---|---|---|---|---|
| 1 | [Preamble text] | [Corresponding product feature or "No corresponding feature identified"] | [Brief analysis applying the frameworks above] | [Literal / DoE / Induced / None] | Yes / No |
| 2 | [Element text] | [Product feature] | [Analysis] | [Theory] | Yes / No |
| ... | ... | ... | ... | ... | ... |

**Strongest Defense Argument Per Covered Element**: For each element marked as covered, state the one strongest argument the accused infringer would make to dispute coverage.

**Overall Assessment**: [1-2 sentences summarizing the strength of the infringement case for this claim, noting any critical gaps.]

After all claims are charted, provide:

### Summary

- **Strongest claims**: Which claims have the strongest infringement case and why.
- **Critical gaps**: Which claim elements are not covered and why.
- **Recommendations**: Suggestions for strengthening the analysis (e.g., additional product information needed, testing that could confirm coverage).

### Coverage Scorecard

| Claim | Elements Covered | Elements Not Covered | Coverage | Strongest Infringement Theory |
|---|---|---|---|---|
| [Claim N] | [count] / [total] | [list uncovered elements] | Full / Partial / None | [Literal / DoE / Induced / None] |
