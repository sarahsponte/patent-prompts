---
name: claims-drafting
description: Draft patent claims from an invention disclosure. Use when the user wants to draft claims, write claims from a disclosure, or generate patent claims for a new invention.
---

# Patent Claims Drafting

Draft patent claims from an invention disclosure, generating one independent claim at the broadest defensible scope plus dependent claims with specific implementation details as fallback positions.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../pre-filing/claims-drafting/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Invention title**
   - **Invention description** (what it does, how it works, what problem it solves)
   - **Key difference/innovation** (what makes it different from existing solutions)
   - **Supporting documents** (optional)
   - **Reference claims** (optional, from a similar patent for style guidance)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to draft the claims
6. Present the output to the user

If the user provides a file path or pasted content as `$ARGUMENTS`, use that as the invention disclosure and extract the needed fields from it.
