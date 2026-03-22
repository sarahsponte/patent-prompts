---
name: detectability-assessment
description: Assess whether infringement of proposed patent claims can be detected in products. Use when the user wants to evaluate claim enforceability or detectability.
---

# Detectability Assessment

Evaluate how easily an invention's implementation can be detected in potentially infringing products, helping decide whether to patent it and how to structure claims for maximum enforceability.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/detectability-assessment/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent claims** or **invention disclosure** to assess
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to perform the assessment
6. Present the output to the user

If the user provides a file path or pasted content as `$ARGUMENTS`, use that as input.
