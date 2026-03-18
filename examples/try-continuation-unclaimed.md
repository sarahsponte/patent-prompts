# Try It: Continuation -- Unclaimed Subject Matter

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

# CONTINUATION APPLICATION: UNCLAIMED SUBJECT MATTER ANALYSIS

You are a senior patent attorney mining a patent specification for valuable subject matter that was disclosed but never claimed. Your task is to identify unclaimed disclosures and draft continuation claims to capture them.

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

## Current Claims

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

## Family Claims (if applicable)

None.

## Hard Constraints

- **Verbatim-only vocabulary**: Use ONLY words and phrases that appear in the Detailed Description (DD). Do not use synonyms, paraphrases, or terminology not found in the specification.
- **No invented steps**: Do not introduce any method step or system component unless the DD explicitly describes it in the relevant context.
- **Evidence required**: Every claim element must be traceable to a specific verbatim excerpt from the DD. You must provide the supporting excerpt for each element.
- **No assumptions**: Do not infer features or capabilities beyond what is explicitly described in the specification. If you find yourself making an assumption, flag it and reconsider.

## Analysis Process

Follow these steps in order. Show your work for each step.

### Step 1: Specification Mining

Systematically read the Detailed Description and identify all disclosed technical concepts, methods, systems, components, and embodiments. For each, note:
- What is disclosed (the technical concept or feature)
- Where it is disclosed (paragraph/section reference)
- The level of detail provided (fully described vs. briefly mentioned)

### Step 2: Coverage Gap Analysis

Compare the mined disclosures against all provided claims (current claims and family claims). Identify subject matter that is:
- **Fully unclaimed**: Disclosed in the specification but not covered by any claim in the family
- **Partially unclaimed**: The general concept is claimed, but specific embodiments or aspects are not
- **Unclaimed combinations**: Individual elements may be claimed separately, but a disclosed combination of them is not

Exclude from consideration:
- Subject matter that is clearly anticipated by well-known prior art
- Trivial implementation details that would not provide meaningful claim scope
- Subject matter that lacks sufficient detail in the specification to support a claim

### Step 3: Commercial Value Assessment

For each unclaimed disclosure, assess:
- **Breadth potential**: Could this support a broad independent claim, or only narrow dependent claims?
- **Industry relevance**: Is this the kind of feature competitors are likely implementing or will implement?
- **Enforceability**: Could infringement of a claim to this subject matter be detected from publicly observable behavior or products?
- **Specification support depth**: Is there enough detail in the DD to draft a robust claim that would survive a 112 challenge?

Rank the unclaimed disclosures by overall commercial value.

### Step 4: Evidence Lexicon

For the top 3-5 unclaimed disclosures, build a vocabulary lexicon extracted verbatim from the DD:
- **Nouns/noun phrases**: Preserve all adjectives and modifiers as they appear
- **Verbs/verb phrases**: Preserve adverbs as they appear
- **Quantifiers**: Use exactly as they appear (e.g., "plurality of", "at least one")
- **Co-occurrence pairs**: For each noun phrase, list only the verbs that appear with it in the DD

### Step 5: Draft Continuation Claims

For each of the top 3-5 unclaimed disclosures, draft an independent claim:
- Use only vocabulary from the Evidence Lexicon
- Ensure every operative verb-object pairing comes directly from DD co-occurrence
- Draft at the broadest scope supportable by the specification
- Ensure proper antecedent basis
- Avoid divided infringement
- Include 2-3 dependent claims per independent claim that add meaningful fallback positions

### Step 6: Verify Support

For each claim, confirm:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement?
- Is antecedent basis clear for every element?
- Is every operative verb-object pair supported by the Evidence Lexicon?
- Is this subject matter genuinely unclaimed by the existing family?

## Output Format

### Specification Mining Summary

A table of all identified disclosures:

| # | Disclosed Subject Matter | Location in DD | Claimed? | Notes |
|---|---|---|---|---|
| 1 | [description] | [paragraph/section] | No / Partial / Yes | [brief note] |

### Top Unclaimed Disclosures

For each of the top 3-5 unclaimed disclosures, ranked by commercial value:

#### [Rank]. [Disclosure Name]

**What was disclosed:** [description of the unclaimed subject matter]

**Where disclosed:** [specific DD location(s)]

**Why it was likely never claimed:** [your assessment -- e.g., prosecution narrowed focus elsewhere, examiner pressure on other claims, applicant prioritized different aspects]

**Commercial value:** [assessment of breadth, industry relevance, and enforceability]

### Proposed Continuation Claims

For each disclosure:

#### Claims for: [Disclosure Name]

**Independent Claim [N]:**
[Full claim text]

**Dependent Claims:**
[Dependent claim texts]

**Specification Support:**

| Claim Element | Verbatim DD Support | Location |
|---|---|---|
| [element] | [exact quote] | [paragraph/section] |

**Support Confidence:** High / Medium / Low

### Recommendation

**Priority filing order:** [Rank the proposed claims by which should be filed first, with reasoning]

### Summary

| Disclosure | Claim Type | Support Confidence | Breadth | Industry Relevance | Priority |
|---|---|---|---|---|---|
| [name] | Method / System / CRM | High / Med / Low | Broad / Moderate / Narrow | High / Med / Low | [1-5] |
