# Try It: Patent Categorization

> Copy everything below the line and paste into any LLM to see this prompt in action.
> This example uses the [sample patent](sample-patent.md) included in this repo.

---

You are a patent portfolio analyst. Categorize the following patent into the most appropriate category and subcategory from the provided taxonomy.

## Patent Information

**Title:** Adaptive Traffic Signal Control System Using Real-Time Pedestrian Detection

**Abstract:**
An adaptive traffic signal control system that dynamically adjusts signal timing based on real-time pedestrian detection and density estimation. The system comprises a plurality of imaging sensors positioned at an intersection, a pedestrian detection module that processes captured image data using a multi-stage classification pipeline, and a signal timing controller that adjusts green phase duration and pedestrian crossing intervals based on detected pedestrian density. The multi-stage classification pipeline includes a motion segmentation stage that isolates moving objects from a background model, a candidate region generator that identifies regions of interest containing potential pedestrians, and a shape classification stage that applies a trained discriminative model to confirm pedestrian presence. The system further incorporates a predictive queue model that estimates future pedestrian arrivals based on historical patterns and current detection data, enabling proactive signal timing adjustments that reduce average pedestrian wait time while maintaining vehicular throughput at the intersection.

## Taxonomy

1. Computer Vision & Image Processing
   1.1 Object Detection & Recognition
   1.2 Image Segmentation
   1.3 Video Analytics
   1.4 Sensor Fusion

2. Transportation & Traffic Systems
   2.1 Traffic Signal Control
   2.2 Vehicle Detection & Tracking
   2.3 Pedestrian Safety Systems
   2.4 Autonomous Vehicles

3. Machine Learning & AI
   3.1 Classification Models
   3.2 Predictive Analytics
   3.3 Neural Networks
   3.4 Natural Language Processing

4. IoT & Connected Systems
   4.1 Sensor Networks
   4.2 Edge Computing
   4.3 Device Communication
   4.4 Smart Infrastructure

5. Data Analytics & Databases
   5.1 Real-Time Analytics
   5.2 Time Series Analysis
   5.3 Data Logging & Auditing
   5.4 Pattern Recognition

## Instructions

1. Read the patent title and abstract carefully.
2. Identify the primary technical field and the core innovation described.
3. Select the single best-fitting **primary category** from the taxonomy.
4. Select the single best-fitting **subcategory** under that primary category. If no subcategory fits well, suggest a new one.
5. Provide your reasoning, referencing specific language from the title and abstract that guided your selection.

If the patent spans multiple categories, choose the one that best represents the **core innovation** (not merely a field of application). For example, a machine-learning method applied to medical imaging should be categorized under its core technical innovation (machine learning or image processing) rather than its application domain (medical devices), unless your taxonomy is organized by application domain.

## Output Format

**Primary Category:** [selected category]
**Subcategory:** [selected subcategory]

**Reasoning:** [2-3 sentences explaining why this category and subcategory best fit the patent, with references to specific language in the title/abstract]

**Confidence:** [High / Medium / Low] -- High if the patent clearly fits one category, Medium if it could fit two categories but one is stronger, Low if the fit is ambiguous.

**Alternative Category (if applicable):** [If confidence is Medium or Low, provide the next-best category and a brief explanation of why it was not selected]
