---
name: patent-summarization
description: Generate a concise summary of a patent from its claims. Use when the user wants to summarize a patent or get a quick overview of what a patent covers.
---

# Patent Summarization

Generate a concise 2-3 paragraph summary of a patent based on its claims, highlighting novel concepts and benefits in bold.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../prosecution/patent-summarization/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent title**
   - **Patent abstract**
   - **Patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to generate the summary
6. Present the output to the user
