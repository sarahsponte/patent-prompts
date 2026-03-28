---
name: draft-review-112
description: Review a patent draft for Section 112 issues including written description, enablement, indefiniteness, and antecedent basis problems. Use when the user wants a focused 112 analysis.
---

# Patent Draft Review (Section 112 Only)

Review a patent draft for Section 112 issues — written description, enablement, indefiniteness, antecedent basis, and means-plus-function problems — providing paste-ready claim amendments and specification additions.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/draft-review/prompt-112.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification** (detailed description)
   - **Patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to perform the review
6. Present the output to the user
