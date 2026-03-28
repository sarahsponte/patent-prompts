---
name: continuation-targeted
description: Draft continuation claims targeting a specific competitor product. Use when the user wants to write continuation claims aimed at a particular product or company.
---

# Continuation Claims - Targeted

Draft targeted continuation claims designed to cover a specific competitor product, using only vocabulary found verbatim in the patent specification and ensuring full written description support under 35 U.S.C. 112.

This skill benefits from **web search** to gather product details.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/continuation-targeted/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification**
   - **Existing patent claims**
   - **Target product description**
   - **Web search results** (optional, or use web search tool if available)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. If web search is available, search for target product technical details
6. Execute the prompt to draft the claims
7. Present the output to the user
