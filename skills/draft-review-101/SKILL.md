---
name: draft-review-101
description: Review a patent draft specifically for Section 101 patent eligibility risks. Use when the user wants a focused 101/Alice analysis.
---

# Patent Draft Review (Section 101 Only)

Review a patent draft for Section 101 patent eligibility risks, evaluating the specification's technical improvement disclosures and providing paste-ready language to strengthen the 101 position.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/draft-review/prompt-101.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification** (detailed description)
   - **Patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to perform the review
6. Present the output to the user
