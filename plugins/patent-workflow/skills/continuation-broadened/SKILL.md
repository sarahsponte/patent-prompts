---
name: continuation-broadened
description: Identify opportunities for broadened continuation claims from an existing patent. Use when the user wants to broaden claim scope in a continuation application.
---

# Continuation - Broadened Claims

Analyze a patent's specification and claims to generate broader independent claims for a continuation application, ensuring every claim element is traceable to the detailed description with verbatim vocabulary support.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/continuation-broadened/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent specification**
   - **Existing patent claims**
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to generate broadened claims
6. Present the output to the user
