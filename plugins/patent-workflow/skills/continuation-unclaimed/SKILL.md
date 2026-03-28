---
name: continuation-unclaimed
description: Find disclosed but unclaimed subject matter for continuation claims. Use when the user wants to identify unclaimed inventions in a patent specification.
---

# Continuation - Unclaimed Subject Matter

Analyze a patent's specification to identify disclosed subject matter that was never claimed, either in the original patent or across the patent family. Generate continuation claims for the most commercially valuable unclaimed disclosures.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/continuation-unclaimed/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification**
   - **Existing patent claims**
   - **Family claims** (optional, claims from related patents)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to identify unclaimed subject matter
6. Present the output to the user
