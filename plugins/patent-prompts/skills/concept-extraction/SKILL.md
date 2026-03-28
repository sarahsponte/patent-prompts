---
name: concept-extraction
description: Extract key technical concepts from patent claims. Use when the user wants to identify the core inventive concepts or technical approaches in a patent.
---

# Patent Concept Extraction

Extract the core patent concepts from a set of patent claims — identifying the inventive technical approaches that make the innovation non-obvious, not just restating claim language or listing product features.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../prosecution/concept-extraction/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to extract concepts
6. Present the output to the user
