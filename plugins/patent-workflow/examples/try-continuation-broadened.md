# Try It: Continuation -- Broadened Claims

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

# CONTINUATION APPLICATION: BROADENED CLAIMS ANALYSIS

You are a senior patent attorney conducting a comprehensive analysis to draft broader independent claims for a continuation application.

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

## Original Claims

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

## Allowed/Amended Claims (if applicable)

None -- no amendments.

## Related Family Claims (if applicable)

None.

## Broadening Claims Analysis Instructions

You are tasked with generating broader independent claims for a continuation application. If both original and allowed/amended claims are provided, assume that amendments were made to overcome prior art cited in office actions. Your goal is to identify where claim scope was narrowed during prosecution and create broader alternatives that avoid the prior art that caused those restrictions.

If only original claims are provided (no amendments), identify strategic broadening opportunities based on the specification while maintaining patentability.

### Analysis Framework:

Begin with a concise checklist (3-7 bullets) outlining the sub-tasks you will complete.

**Step 1. Identify Narrowing and Broadening Opportunities:**
- If amended claims exist, compare originally filed claims with the allowed/amended claims
- Identify limitations that were added or narrowed during prosecution
- Identify limitations in the allowed claims that could potentially be broadened without reintroducing prior art issues
- If no amendments exist, analyze the originally filed claims for unnecessarily narrow limitations

**Step 2. Build Evidence Lexicon (internal reasoning only):**
- Extract only verbatim verbs, nouns, adjectives, adverbs, and quantifiers from the Detailed Description (DD)
- For each noun phrase, preserve any adjectives/modifiers that appear with it in the DD (e.g., "real-time processing" not just "processing")
- Preserve adverbs with their verbs as they appear (e.g., "automatically generates", "dynamically adjusts")
- Track quantifiers exactly as used in the DD (e.g., "plurality of", "at least one", "one or more")
- For each noun phrase (with its modifiers), include only those verbs (with their adverbs) that locally co-occur with the noun in the DD

**Step 3. Draft Broadened Claims:**
- Create 3-5 independent claims, each broader than the current version
- Ensure every operative verb-object pair is strictly supported by the Evidence Lexicon
- Explicitly link all broader elements to verbatim DD support
- Mimic the style and claim types of the original claims
- Avoid concepts that are likely to be prior art
- Ensure antecedent basis is clear; do not use "the" if the antecedent is not established
- Avoid divided infringement claims (claims that require multiple entities to infringe)

**Step 4. Verify Claim-to-Evidence Mapping (internal QC):**
- Confirm that every phrase and object in each claim element corresponds to a verbatim DD quotation with a specific location identifier

**Step 5. Assess Support Confidence (internal use):**
- **High:** All elements fully mapped to verbatim DD support with clear local co-occurrence
- **Medium:** Most elements mapped; some concerns about specificity or co-occurrence
- **Low:** Major concerns regarding support or co-occurrence remain

**Step 6. Select Best Recommendation:**
- Evaluate all drafted claims considering support confidence, breadth, and commercial applicability
- Select the claim with the strongest potential for broad applicability

## Hard Constraints (must follow)

- **Verbatim-only vocabulary:** Use exclusively words and phrases found in the Detailed Description; absolutely no synonyms or paraphrases
- **No invented steps:** Do not introduce any step that is not explicitly linked to the same data flow in the DD
- **Evidence required:** Every claim element must be traceable to verbatim DD excerpts, including specific location identifiers (paragraph or section numbers)
- **No assumptions:** Do not speculate on competitor or applicant behavior. If you begin to make an assumption, flag it and reconsider that claim element

## BEFORE FINALIZING

Before producing your final claims, verify:
- Does every claim element trace to verbatim language in the Detailed Description?
- Have I introduced divided infringement (requiring multiple entities to perform different steps)?
- Is antecedent basis clear for every element ("a" for first mention, "the" for subsequent)?
- Does any broadened claim reintroduce limitations that were narrowed to overcome specific prior art?
- Is every operative verb-object pair supported by the Evidence Lexicon?

## OUTPUT FORMAT

For each broadened claim, provide:

### Broadened Claim [Number]

**Claim Text:**
[The full claim text, formatted as a proper patent claim with preamble, transitional phrase, and body elements]

**Broadening Strategy:**
[Explanation of how this claim is broader than the original/allowed claims and what limitations were removed or generalized]

**Specification Support:**
[Verbatim excerpt(s) from the specification (including figure/paragraph references) that support the broader claim language]

---

After all claims, provide:

### Recommended Claim

**Selected Claim:** [Number]

**Reasoning:** [2-3 sentences explaining why this claim is the best choice for broadening -- consider support confidence, breadth of coverage, and commercial applicability]

### Claim Support Confidence Summary

| Claim | Support Confidence | Key Broadening | Risk of 112 Rejection |
|---|---|---|---|
| [Claim N] | High / Medium / Low | [what was broadened] | [specific 112 risk, if any] |
