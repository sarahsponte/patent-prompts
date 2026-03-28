---
name: prior-art-analysis
description: Analyze patent claims against prior art using 35 U.S.C. 102/103 framework. Use when the user wants prior art analysis, novelty assessment, or obviousness evaluation.
---

# Prior Art Analysis

Analyze independent patent claims against prior art using the full 35 U.S.C. 102 (anticipation) and 103 (obviousness) framework, including Graham v. John Deere factors and KSR rationales.

This skill benefits from **web search** to find relevant prior art references.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/prior-art-analysis/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent claims** (independent claims to analyze)
   - **Known prior art** (optional)
   - **Web search results** (optional, or use web search tool if available)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. If web search is available, search for relevant prior art references
6. Execute the prompt to perform the analysis
7. Present the output to the user
