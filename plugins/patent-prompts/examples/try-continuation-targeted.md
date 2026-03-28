# Try It: Continuation Claims -- Targeted

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

You are a senior patent attorney drafting continuation claims targeted at a specific competitor product. Your task is to draft new independent claims for a continuation application that are (a) fully supported by the patent specification and (b) designed to cover the described competitor product.

## Patent Specification (Detailed Description)

The present invention relates to an adaptive traffic signal control system that dynamically adjusts signal timing at intersections based on real-time pedestrian detection and density estimation.

**System Architecture.** Referring to FIG. 1, the system 100 comprises a plurality of imaging sensors 110 positioned at an intersection 105. The imaging sensors 110 include at least one visible-light camera 112 and at least one infrared sensor 114, each directed toward at least one crosswalk area 120. The imaging sensors 110 are communicatively coupled to a processing unit 130 that includes a processor 132 and a memory 134. The processing unit 130 executes a pedestrian detection module 140, a predictive queue model 150, and a signal timing controller 160.

**Pedestrian Detection Module.** The pedestrian detection module 140 processes each captured image frame through a multi-stage classification pipeline 200. As shown in FIG. 2, the multi-stage classification pipeline 200 comprises three sequential stages. The first stage is a motion segmentation stage 210 that isolates moving objects from a background model 215. The background model 215 is maintained using an adaptive learning rate that increases during periods of low traffic activity and decreases during periods of high traffic activity, thereby ensuring rapid adaptation to changing environmental conditions such as shifting shadows or varying illumination. The motion segmentation stage 210 produces a set of motion regions 220 representing areas of the image frame where movement has been detected.

The second stage is a candidate region generator 230 that identifies, from the set of motion regions 220, regions of interest 235 containing potential pedestrians. The candidate region generator 230 applies spatial filtering to exclude regions that are too small or too large to represent a human figure, based on calibrated size thresholds that account for the distance between the imaging sensor 110 and the crosswalk area 120.

The third stage is a shape classification stage 240 that applies a trained discriminative model 245 to each region of interest 235 to generate a pedestrian confidence score 250. In one embodiment, the trained discriminative model 245 comprises a histogram of oriented gradients (HOG) feature extractor coupled with a support vector machine (SVM) classifier. The pedestrian detection module 140 determines a pedestrian density value 260 for the at least one crosswalk area 120 by counting the number of regions of interest 235 having a pedestrian confidence score 250 exceeding a configurable detection threshold 255. The configurable detection threshold 255 may be dynamically adjusted based on ambient lighting conditions measured by a photometric sensor 116 positioned at the intersection 105.

**Predictive Queue Model.** The predictive queue model 150 generates an estimated future pedestrian arrival rate 310 based on the current pedestrian density value 260 and historical pedestrian traffic patterns 320 stored in a pattern database 155. The predictive queue model 150 applies a weighted moving average to the historical pedestrian traffic patterns 320, with more recent patterns receiving a higher weight, to account for evolving pedestrian behavior trends such as seasonal changes or new nearby construction. The estimated future pedestrian arrival rate 310 enables the system to proactively adjust signal timing before pedestrian congestion occurs rather than merely reacting to current conditions.

**Signal Timing Controller.** The signal timing controller 160 adjusts at least one of a green phase duration 410 and a pedestrian crossing interval 420 based on the pedestrian density value 260 and the estimated future pedestrian arrival rate 310. When the pedestrian density value 260 exceeds a high-density threshold, the signal timing controller 160 extends the pedestrian crossing interval 420 to provide adequate crossing time. The signal timing controller 160 further detects a pedestrian group comprising three or more pedestrians within a defined spatial proximity and extends the pedestrian crossing interval 420 by a group accommodation factor 425 to ensure the group can safely complete crossing.

The signal timing controller 160 transmits the adjusted green phase duration 410 to an adjacent intersection controller 170 via a dedicated communication link 175 to coordinate signal timing across a plurality of intersections, thereby creating a coordinated "green wave" effect for pedestrian corridors. A display unit 180 presents the pedestrian density value 260 and signal timing parameters to a traffic management operator in real time. An audit database 190 logs the pedestrian density value 260 and signal timing adjustment data for subsequent performance analysis.

**Data Fusion.** In embodiments where both infrared sensor 114 and visible-light camera 112 are present, the pedestrian detection module 140 fuses data from the infrared sensor 114 and the visible-light camera 112 to improve detection accuracy in low-light conditions. The infrared sensor 114 captures thermal signatures of pedestrians that remain detectable regardless of ambient lighting, while the visible-light camera 112 provides higher-resolution spatial detail during daylight conditions. The fusion algorithm assigns dynamic weights to each sensor modality based on the ambient lighting conditions, favoring infrared data during nighttime and visible-light data during daytime.

## Current Claims of the Patent Family

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

## Competitor Product Description

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

### Search 1: "SmartCross CityFlow Technologies pedestrian safety platform architecture"

**CityFlow Technologies — SmartCross Product Page**
SmartCross is an AI-powered pedestrian safety platform for urban intersections. Uses pole-mounted dual-sensor units combining thermal imaging and HD visible-light cameras. Detects and counts pedestrians at crosswalks in real time. Integrates with existing traffic signal controllers via NTCIP protocol. Each intersection unit runs the CityFlow PedSense detection engine on an edge computing module.

**CityFlow Technologies — SmartCross Technical Datasheet (PDF excerpt)**
Detection Pipeline: PedSense v3.2 uses a three-stage architecture: (1) frame differencing against an adaptive background model to identify motion regions, (2) spatial filtering to extract candidate pedestrian regions based on calibrated size thresholds, (3) CNN classifier assigning a detection confidence score per candidate. Confidence threshold is operator-configurable (default 0.85). Outputs per-crosswalk pedestrian count every 500ms. Sensor fusion mode available: assigns dynamic weights to thermal and visible-light inputs based on ambient lighting conditions.

### Search 2: "SmartCross predictive timing group detection features"

**CityFlow Blog — "SmartCross v4.0: Predictive Timing and Group Detection" (March 2024)**
New in v4.0: Predictive signal timing analyzes historical pedestrian volume data (stored per-intersection) alongside real-time counts to forecast near-term demand. Preemptively extends pedestrian phases before congestion builds. Group detection feature identifies clusters of 3 or more pedestrians waiting at a crosswalk and adds extra crossing time automatically. Inter-intersection communication shares timing data with neighboring SmartCross units to create coordinated pedestrian corridors. Operator dashboard displays live pedestrian counts, predicted demand curves, and signal status.

## Family Claims (Optional Context)

None.

## Hard Constraints

- **Verbatim-only vocabulary**: Use ONLY words and phrases that appear in the Detailed Description (DD). Do not use synonyms, paraphrases, or terminology not found in the specification.
- **No invented steps**: Do not introduce any method step or system component unless the DD explicitly describes it in the relevant context.
- **Evidence required**: Every claim element must be traceable to a specific verbatim excerpt from the DD. You must provide the supporting excerpt for each element.
- **No assumptions**: Do not infer actions or features the competitor "would likely" use. If you find yourself making an assumption, flag it and reconsider the element.

## Analysis Process

Follow these steps in order. Show your work for each step.

### Step 1: Concept Selection

Analyze the competitor product description against the patent specification. Identify 2-4 technical concepts from the specification that:
- Are implemented by the competitor product (based on the description provided)
- Have strong written description support in the DD
- Are not already fully covered by the current claims
- Have commercial significance

For each selected concept, explain why it was chosen and what gap it fills relative to the existing claims.

### Step 2: Evidence Lexicon

For each selected concept, build a vocabulary lexicon extracted verbatim from the DD:
- **Nouns/noun phrases**: Preserve all adjectives and modifiers as they appear (e.g., "real-time processing" not just "processing")
- **Verbs/verb phrases**: Preserve adverbs as they appear (e.g., "automatically generates" not just "generates")
- **Quantifiers**: Use exactly as they appear (e.g., "plurality of", "at least one", "one or more")
- **Co-occurrence pairs**: For each noun phrase, list only the verbs that appear with it in the DD. Do not recombine terms that do not co-occur in the specification.

### Step 3: Draft Targeted Claims

Draft 3-5 independent claims. For each claim:
- Use only vocabulary from the Evidence Lexicon built in Step 2
- Ensure every operative verb-object pairing comes directly from DD co-occurrence
- Target the competitor product as described
- Mimic the style and claim types (method, system, CRM) of the existing claims in the family
- Ensure proper antecedent basis -- do not use "the" for an element that has not been previously introduced in the claim
- Avoid divided infringement -- each claim should be infringeable by a single entity performing all steps or owning all components
- Avoid concepts that are clearly anticipated by prior art

### Step 4: Claim-Evidence Mapping

For each claim, provide a mapping table:

| Claim Element | Verbatim DD Support | Location in Specification |
|---|---|---|
| [element text] | [exact quote from DD] | [paragraph/section reference] |

### Step 5: Support Confidence Assessment

Rate each claim:
- **High**: All elements fully mapped to verbatim DD excerpts with clear co-occurrence
- **Medium**: Most elements mapped, minor concerns about specificity
- **Low**: Notable gaps in DD support

Only recommend claims rated High or Medium.

### Step 6: Competitive Analysis

For each claim, analyze:
- How the claim maps to the described competitor product features
- Whether the claim is broad enough to cover reasonable design-arounds
- Which claim elements provide the strongest competitive protection (hardest to design around)

### Step 7: Best Recommendation

Select the single best claim from your set and explain why it is the strongest choice, considering:
- Specification support strength
- Breadth of coverage against the competitor product
- Difficulty for the competitor to design around
- Likelihood of allowance (distinction from existing claims and likely prior art)

## BEFORE FINALIZING

Before producing your final claims, verify:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement (requiring multiple entities to perform different steps)?
- Is antecedent basis clear for every element ("a" for first mention, "the" for subsequent)?
- Is every operative verb-object pair supported by the Evidence Lexicon?
- Does each claim map to a concrete feature in the competitor product description (not an inference)?

## Output Format

Provide your full analysis in markdown with the following sections:

### Selected Concepts
For each concept: name, description, rationale for selection, and DD support summary.

### Evidence Lexicon
The verbatim vocabulary extracted for each concept, organized by concept.

### Targeted Claims
Each claim with:
- Full claim text
- Targeted product feature mapping (how this claim reads on the competitor product)
- Specification support (verbatim DD excerpts with location references)

### Claim-Evidence Mapping Table
The mapping table from Step 4 for each claim.

### Support Confidence
Confidence rating and explanation for each claim.

### Competitive Analysis
Analysis from Step 6.

### Recommendation
Your best claim recommendation with full reasoning.

### Claim Support Confidence Summary

| Claim | Support Confidence | Competitor Coverage | Key Vulnerability |
|---|---|---|---|
| [Claim N] | High / Medium / Low | [which product features mapped] | [strongest design-around or 112 risk] |
