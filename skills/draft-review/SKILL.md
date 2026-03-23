---
name: draft-review
description: Review a patent application draft for Section 101 eligibility and Section 112 issues before filing. Use when the user wants to review a patent draft.
---

# Patent Draft Review (101 + 112 Combined)

Review a patent draft (specification and claims) for both Section 101 eligibility risks and Section 112 issues before filing, providing a prioritized list of problems with paste-ready remedies.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/draft-review/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification** (detailed description)
   - **Patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to perform the review
6. Present the output to the user

## Variants

For focused reviews, also available:
- `/patent-prompts:draft-review-101` — Section 101 only
- `/patent-prompts:draft-review-112` — Section 112 only

If the user provides a file path or pasted content as `$ARGUMENTS`, use that as the draft.
