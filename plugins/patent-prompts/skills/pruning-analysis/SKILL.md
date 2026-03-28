---
name: pruning-analysis
description: Evaluate whether a patent should be maintained or abandoned. Use when the user wants to analyze a patent for pruning, maintenance decisions, or portfolio optimization.
---

# Patent Pruning Analysis

Evaluate whether a patent case should be maintained or pruned based on claim scope analysis relative to other cases in the same patent family. Produces a determination of BROADEST, COMPLEMENTARY, NARROW, SUNSET, or REVIEW with supporting reasoning.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/pruning-analysis/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent claims**
   - **Patent family information** (other patents in the family)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to perform the analysis
6. Present the output to the user
