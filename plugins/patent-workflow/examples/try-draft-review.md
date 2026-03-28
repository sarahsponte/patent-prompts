# Try It: Draft Review (101 + 112)

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

# PATENT DRAFT REVIEW: SECTION 101 AND SECTION 112 ANALYSIS

You are an expert patent attorney. Your task is to analyze a draft patent specification and claims BEFORE filing to identify potential Section 101 eligibility risks and Section 112 issues, and provide actionable recommendations to fix them.

## OBJECTIVE

Proactively identify 101 and 112 vulnerabilities in the draft so they can be fixed before filing, avoiding rejections and strengthening the patent application.

## INPUT

<PATENT_DRAFT>
# Adaptive Traffic Signal Control System Using Real-Time Pedestrian Detection

## Abstract

An adaptive traffic signal control system that dynamically adjusts signal timing based on real-time pedestrian detection and density estimation. The system comprises a plurality of imaging sensors positioned at an intersection, a pedestrian detection module that processes captured image data using a multi-stage classification pipeline, and a signal timing controller that adjusts green phase duration and pedestrian crossing intervals based on detected pedestrian density. The multi-stage classification pipeline includes a motion segmentation stage that isolates moving objects from a background model, a candidate region generator that identifies regions of interest containing potential pedestrians, and a shape classification stage that applies a trained discriminative model to confirm pedestrian presence. The system further incorporates a predictive queue model that estimates future pedestrian arrivals based on historical patterns and current detection data, enabling proactive signal timing adjustments that reduce average pedestrian wait time while maintaining vehicular throughput at the intersection.

## Claims

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

## Specification (Detailed Description)

The present invention relates to an adaptive traffic signal control system that dynamically adjusts signal timing at intersections based on real-time pedestrian detection and density estimation.

**System Architecture.** Referring to FIG. 1, the system 100 comprises a plurality of imaging sensors 110 positioned at an intersection 105. The imaging sensors 110 include at least one visible-light camera 112 and at least one infrared sensor 114, each directed toward at least one crosswalk area 120. The imaging sensors 110 are communicatively coupled to a processing unit 130 that includes a processor 132 and a memory 134. The processing unit 130 executes a pedestrian detection module 140, a predictive queue model 150, and a signal timing controller 160.

**Pedestrian Detection Module.** The pedestrian detection module 140 processes each captured image frame through a multi-stage classification pipeline 200. As shown in FIG. 2, the multi-stage classification pipeline 200 comprises three sequential stages. The first stage is a motion segmentation stage 210 that isolates moving objects from a background model 215. The background model 215 is maintained using an adaptive learning rate that increases during periods of low traffic activity and decreases during periods of high traffic activity, thereby ensuring rapid adaptation to changing environmental conditions such as shifting shadows or varying illumination. The motion segmentation stage 210 produces a set of motion regions 220 representing areas of the image frame where movement has been detected.

The second stage is a candidate region generator 230 that identifies, from the set of motion regions 220, regions of interest 235 containing potential pedestrians. The candidate region generator 230 applies spatial filtering to exclude regions that are too small or too large to represent a human figure, based on calibrated size thresholds that account for the distance between the imaging sensor 110 and the crosswalk area 120.

The third stage is a shape classification stage 240 that applies a trained discriminative model 245 to each region of interest 235 to generate a pedestrian confidence score 250. In one embodiment, the trained discriminative model 245 comprises a histogram of oriented gradients (HOG) feature extractor coupled with a support vector machine (SVM) classifier. The pedestrian detection module 140 determines a pedestrian density value 260 for the at least one crosswalk area 120 by counting the number of regions of interest 235 having a pedestrian confidence score 250 exceeding a configurable detection threshold 255. The configurable detection threshold 255 may be dynamically adjusted based on ambient lighting conditions measured by a photometric sensor 116 positioned at the intersection 105.

**Predictive Queue Model.** The predictive queue model 150 generates an estimated future pedestrian arrival rate 310 based on the current pedestrian density value 260 and historical pedestrian traffic patterns 320 stored in a pattern database 155. The predictive queue model 150 applies a weighted moving average to the historical pedestrian traffic patterns 320, with more recent patterns receiving a higher weight, to account for evolving pedestrian behavior trends such as seasonal changes or new nearby construction. The estimated future pedestrian arrival rate 310 enables the system to proactively adjust signal timing before pedestrian congestion occurs rather than merely reacting to current conditions.

**Signal Timing Controller.** The signal timing controller 160 adjusts at least one of a green phase duration 410 and a pedestrian crossing interval 420 based on the pedestrian density value 260 and the estimated future pedestrian arrival rate 310. When the pedestrian density value 260 exceeds a high-density threshold, the signal timing controller 160 extends the pedestrian crossing interval 420 to provide adequate crossing time. The signal timing controller 160 further detects a pedestrian group comprising three or more pedestrians within a defined spatial proximity and extends the pedestrian crossing interval 420 by a group accommodation factor 425 to ensure the group can safely complete crossing.

The signal timing controller 160 transmits the adjusted green phase duration 410 to an adjacent intersection controller 170 via a dedicated communication link 175 to coordinate signal timing across a plurality of intersections, thereby creating a coordinated "green wave" effect for pedestrian corridors. A display unit 180 presents the pedestrian density value 260 and signal timing parameters to a traffic management operator in real time. An audit database 190 logs the pedestrian density value 260 and signal timing adjustment data for subsequent performance analysis.

**Data Fusion.** In embodiments where both infrared sensor 114 and visible-light camera 112 are present, the pedestrian detection module 140 fuses data from the infrared sensor 114 and the visible-light camera 112 to improve detection accuracy in low-light conditions. The infrared sensor 114 captures thermal signatures of pedestrians that remain detectable regardless of ambient lighting, while the visible-light camera 112 provides higher-resolution spatial detail during daylight conditions. The fusion algorithm assigns dynamic weights to each sensor modality based on the ambient lighting conditions, favoring infrared data during nighttime and visible-light data during daytime.
</PATENT_DRAFT>

---

# PART 1: SECTION 101 ELIGIBILITY ANALYSIS

## Technical Improvement Disclosure Framework

Based on USPTO guidance and Federal Circuit precedent, specifications that successfully support 101 eligibility typically include:

### 1. Technical Improvement Disclosure (Critical)
Per Enfish, the specification should explain improvements to:
- How the computer/system itself operates (not just using it as a tool)
- Specific technical capabilities that are enhanced
- Measurable or observable technical benefits

**Key Language Patterns:**
- "reduces processing time by..."
- "decreases memory/storage requirements..."
- "improves accuracy/precision of..."
- "enables real-time processing that was previously not possible..."
- "reduces system complexity by..."
- "eliminates the need for [prior technical component]..."

### 2. Technical Mechanism/Solution (Critical)
Per McRO, include specific rules/steps, not just desired results:
- Detailed algorithmic steps with specific operations
- Data structures and their specific configurations
- System architecture with component interactions
- Processing flows with defined decision points
- Explain HOW the invention works, not just WHAT result it achieves

## 101 Analysis Steps

### Step 1: Identify the Core Technical Contribution
1. What is the invention actually doing? Distinguish between the technical implementation and the business/functional goal.
2. How does it improve technology? Does the spec explain improvement to computer/system functionality, or is the computer just a tool to implement an abstract idea?

### Step 2: Case Law Alignment
Evaluate alignment with favorable 101 precedent:
- **Enfish**: Does spec describe improvement to computer functionality itself?
- **McRO**: Does spec include specific rules/steps (not just results)?
- **DDR Holdings**: Does spec describe technology-specific solution to technology-specific problem?
- **Visual Memory**: Does spec describe improved technical architecture?

### Step 3: Gap Analysis
Identify specific gaps using the severity framework below and provide concrete recommendations.

---

# PART 2: SECTION 112 ANALYSIS

## 112 Issue Types to Check

### 112(a) Written Description Issues
The specification must describe the claimed invention such that one skilled in the art would recognize the inventor had possession of the invention.

**Common Problems:**
- Claim recites element not described in specification
- Claim scope broader than what specification supports
- Genus claimed but only species described
- Functional language without structural support

**What to Look For:**
- Each claim element must have explicit support in the spec
- Claim scope must be supported by the spec's full breadth
- New terms in claims must be defined or described in spec

### 112(a) Enablement Issues
The specification must enable one skilled in the art to make and use the full scope of the claimed invention without undue experimentation.

**Wands Factors (use to assess enablement risk):**
1. Quantity of experimentation necessary
2. Amount of direction or guidance presented
3. Presence or absence of working examples
4. Nature of the invention
5. State of the prior art
6. Relative skill of those in the art
7. Predictability or unpredictability of the art
8. Breadth of the claims

### 112(b) Indefiniteness Issues
Claims must particularly point out and distinctly claim the subject matter with reasonable certainty.

**Common Problems:**
- Ambiguous terms without definition
- Relative terms without reference point (e.g., "substantially," "about")
- Terms of degree without guidance
- Unclear antecedent basis

### Antecedent Basis Issues
A subset of indefiniteness where "the" or "said" is used without prior introduction.

**What to Look For:**
- Every use of "the [element]" or "said [element]" must have a prior introduction
- Dependent claims must have proper basis in their parent claims

### 112(f) Means-Plus-Function Issues
Claim limitations using "means for" or "step for" language invoke 112(f) and are limited to corresponding structure in the specification.

**3-Prong Test for Invoking 112(f):**
1. Uses "means for", "step for", "module for", "mechanism for", "unit for", or "device for"
2. The term is modified by functional language (describes what it does, not what it is)
3. The term is NOT modified by sufficient structure to perform the function

**If 112(f) Term Found Without Structure:**
- Add structural language to claim to avoid 112(f) interpretation, OR
- Add corresponding structure to specification with clear linkage to the function

---

# SEVERITY FRAMEWORK (applies to both 101 and 112)

Classify each issue as High, Medium, or Low severity. Err on the side of fewer false positives.

### High Severity (must address before filing)
- **101**: No technical improvement disclosure; no technical mechanism; pure business improvement only
- **112**: Antecedent basis issues; claim elements with NO support in spec; 112(f) terms with NO corresponding structure; clear indefiniteness

### Medium Severity (should address)
- **101**: Weak/vague improvement disclosure; incomplete mechanism; generic implementation language
- **112**: Partial/weak spec support; 112(f) terms with unclear structural linkage; relative terms without clear reference; enablement gaps

### Low Severity (nice to have)
- **101**: Adequate disclosure that could benefit from additional detail; missing secondary benefits
- **112**: Terms clear to POSITA but not explicitly defined; minor scope questions; stylistic indefiniteness

---

# OUTPUT FORMAT

## Section 101 Analysis

### Overall 101 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest 101 risk, or "No significant 101 issues identified"]

### 101 Recommendations

For each recommendation:

**[Number]. [Brief description of the gap]** -- Severity: [High/Medium/Low]

- **Why It Matters:** [How this strengthens 101 position]
- **Where to Add:** [Reference to the section/paragraph in the draft where this should be added]
- **Paste-Ready Language:**
  > [Specification text ready to copy into the draft]

---

## Section 112 Analysis

### Overall 112 Risk: [High / Medium / Low]

**Primary Risk:** [1-2 sentence summary of the biggest issue, or "No significant 112 issues identified"]

### 112 Issues

For each issue:

**[Number]. [Issue Type] -- Claims [affected claim numbers]** -- Severity: [High/Medium/Low]

- **Problem:** [Description of the issue]
- **Claim Text:** "[Quote the specific claim text causing the issue]"
- **Remedy:**
  - [If spec change needed] **Add to Specification:**
    > [Paste-ready specification text]
  - [If claim change needed] **Original Claim Text:**
    > [Verbatim original text]
  - [If claim change needed] **Amended Claim Text:**
    > [Paste-ready replacement text]

## Review Summary

| Category | High Severity | Medium Severity | Low Severity | Total |
|---|---|---|---|---|
| 101 Issues | [count] | [count] | [count] | [count] |
| 112(a) Written Description | [count] | [count] | [count] | [count] |
| 112(a) Enablement | [count] | [count] | [count] | [count] |
| 112(b) Indefiniteness | [count] | [count] | [count] | [count] |
| 112(f) Means-Plus-Function | [count] | [count] | [count] | [count] |

**Bottom Line:** [1-2 sentences: Is this draft ready to file, or are there blocking issues?]

---

## IMPORTANT NOTES

- If no issues are found for a section, state "No significant [101/112] issues identified" and provide an empty list
- All recommended language must be paste-ready -- counsels will copy and paste directly into the draft
- For claim amendments, use ONLY vocabulary from the specification (no synonyms or paraphrases)
- For specification additions, you may introduce new framing language to articulate benefits
- Focus on TECHNICAL improvements, not business improvements
- Do NOT suggest quantitative metrics, benchmarks, or performance numbers that would require experimentation
- Do NOT suggest pseudocode, flowcharts, or programming-style syntax -- use patent specification prose
- This is a pre-filing review, so adding new content IS appropriate (no "new matter" concerns)
