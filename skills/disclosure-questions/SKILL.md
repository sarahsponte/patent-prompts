---
name: disclosure-questions
description: Generate strategic clarifying questions for an invention disclosure before patent drafting. Use when the user has a disclosure and wants to strengthen it.
---

# Disclosure Questions

Generate 10 strategic questions for enriching an invention disclosure before patent drafting. Questions span technical clarification, inventive insight extraction, claim strategy, alternative embodiments, and commercial context.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/disclosure-questions/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Invention disclosure** content
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to generate the questions
6. Present the output to the user

If the user provides a file path or pasted content as `$ARGUMENTS`, use that as the disclosure.
