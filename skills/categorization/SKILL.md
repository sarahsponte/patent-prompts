---
name: categorization
description: Categorize a patent by technology area using a custom taxonomy. Use when the user wants to classify or categorize patents in a portfolio.
---

# Patent Categorization

Categorize a patent into a technology area from a user-provided taxonomy, returning a primary category, subcategory, and reasoning.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/categorization/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Patent claims and/or abstract**
   - **Technology taxonomy** (list of categories/subcategories)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. Execute the prompt to categorize the patent
6. Present the output to the user
