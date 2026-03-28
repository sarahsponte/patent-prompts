# Try It: Patent Pruning Analysis

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

# PATENT PRUNING FAMILY ANALYSIS

## Context

You are a patent portfolio analyst evaluating whether a patent case should be maintained or pruned based on claim scope analysis relative to other cases in the same patent family.

## Target Case for Analysis

- Docket Number: TC-2019-0042
- Country: US
- Status: Granted (US Patent No. 11,234,567)
- Years Remaining: 12
- First Independent Claim:
1. A method for controlling traffic signals at an intersection, the method comprising:
   - capturing, by a plurality of imaging sensors positioned at the intersection, a sequence of image frames of at least one crosswalk area;
   - processing, by a pedestrian detection module, each image frame through a multi-stage classification pipeline, the multi-stage classification pipeline comprising:
     - a motion segmentation stage that isolates moving objects from a background model to produce a set of motion regions;
     - a candidate region generator that identifies, from the set of motion regions, regions of interest containing potential pedestrians; and
     - a shape classification stage that applies a trained discriminative model to each region of interest to generate a pedestrian confidence score;
   - determining, by the pedestrian detection module, a pedestrian density value for the at least one crosswalk area based on the pedestrian confidence scores exceeding a configurable detection threshold;
   - generating, by a predictive queue model, an estimated future pedestrian arrival rate based on the pedestrian density value and historical pedestrian traffic patterns stored in a pattern database; and
   - adjusting, by a signal timing controller, at least one of a green phase duration and a pedestrian crossing interval based on the pedestrian density value and the estimated future pedestrian arrival rate.

## Other Cases in Same Jurisdiction (US)

Case: TC-2021-0088 (US)
Status: Granted (US Patent No. 11,567,890)
Years Remaining: 15
First Independent Claim: A system for monitoring pedestrian activity at a traffic intersection, comprising: a plurality of cameras positioned to capture images of crosswalk areas; a processing unit configured to: apply a background subtraction algorithm to isolate moving objects in the captured images; classify each moving object as a pedestrian or non-pedestrian using a machine learning model; determine a count of pedestrians present in each crosswalk area; and transmit the pedestrian count to a traffic management server via a network interface.

Case: TC-2022-0155 (US)
Status: Pending (Application No. 17/890,123)
Years Remaining: 18 (if granted)
First Independent Claim: A method for adaptive traffic signal control comprising: receiving pedestrian detection data from a sensor array at an intersection; computing a pedestrian flow metric based on the detection data and time-weighted historical averages; comparing the pedestrian flow metric to a dynamic threshold; and when the pedestrian flow metric exceeds the dynamic threshold, extending a pedestrian crossing phase duration by a computed extension value proportional to the pedestrian flow metric.

## Other Cases in Extended Family (Other Jurisdictions)

Case: TC-2020-0042-EP (EP)
Status: Granted (EP Patent No. 3,456,789)
Years Remaining: 13
First Independent Claim: A method for controlling traffic signals at an intersection based on real-time pedestrian detection, the method comprising: capturing image frames from imaging sensors at the intersection; processing each image frame to detect pedestrians using a multi-stage classification pipeline; determining a pedestrian density value based on detected pedestrians; and adjusting a signal timing parameter based on the pedestrian density value.

## Instructions

Analyze the target case's first independent claim against other ALIVE cases in the SAME jurisdiction only. Consider both claim scope AND remaining patent life.

### Determination Criteria (evaluate in this order):

**REVIEW** -- Return this FIRST if:
- Target case is "Pending (published application)" -- these are not yet issued and cannot be classified by claim scope
- Comparison is uncertain (complex claim language)
- Claims have overlapping but partially distinct coverage that is hard to categorize
- Missing claim data prevents analysis
- Edge case requiring human judgment

**SUNSET** -- Return this if:
- Target case is "Issued (enforceable)" AND has less than 3 years remaining patent life
- Note: SUNSET only applies to issued patents, never to pending applications
- Note in reasoning whether coverage is maintained by longer-lived cases in the jurisdiction

**BROADEST** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- AND one of:
  - No other ALIVE cases exist in the same jurisdiction
  - Target claim is the BROADEST among all alive cases in this jurisdiction (fewest limitations, covers most embodiments)

**COMPLEMENTARY** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- Target claim covers DISTINCT subject matter not covered by any other alive case (e.g., different apparatus vs method, different technical approach)
- The claim is not simply narrower -- it covers genuinely different aspects

**NARROW** -- Return this if ALL conditions apply:
- Target case is "Issued (enforceable)" with 3+ years remaining patent life
- At least one other ALIVE case exists in the same jurisdiction
- AND one of:
  - Target claim is NARROWER than another alive case (adds more limitations, covers subset of embodiments)
  - Target claim has DUPLICATE/EQUIVALENT scope to another alive case

### Analysis Guidelines:
- A claim is "broader" if it covers more embodiments with fewer limitations
- A claim is "narrower" if it adds specific limitations that reduce scope
- "Complementary" means genuinely different coverage (e.g., method vs apparatus, different inventive concept), NOT just a narrower version
- Consider both apparatus and method claim distinctions
- Status is evaluated FIRST -- a pending (published) application is always REVIEW regardless of scope
- Age is evaluated SECOND -- an issued case with less than 3 years is SUNSET regardless of scope
- If target case has no claims available, return REVIEW with appropriate reasoning

## OUTPUT FORMAT

### Determination: [BROADEST / COMPLEMENTARY / NARROW / SUNSET / REVIEW]

**Reasoning:** [2-3 sentences explaining your determination. Refer to the target case as "this case" and reference other cases by their docket numbers. Describe the factual basis for your analysis -- years remaining, claim scope comparisons, etc.]

**Broader Cases in Jurisdiction:** [List docket numbers of cases with broader claims than the target in the same country. Write "None" if target is broadest or complementary.]

### Recommendation

[1-2 sentences on the portfolio action: maintain, consider abandoning, flag for attorney review, etc.]
