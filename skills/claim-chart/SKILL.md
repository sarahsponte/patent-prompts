---
name: claim-chart
description: Map patent claims to product features for infringement analysis. Use when the user wants a claim chart, infringement analysis, or to map claims against a product.
---

# Claim Chart Generation

Generate a detailed claim chart mapping patent claim elements to features of an accused product, applying literal infringement, induced infringement, and doctrine of equivalents analysis with strict anti-speculation rules.

This skill benefits from **web search** to gather product technical details.

## Instructions

1. Read the prompt file at `${CLAUDE_SKILL_DIR}/../../portfolio/claim-chart/prompt.md`
2. Extract the prompt section (between the `---` delimiters)
3. Ask the user for the required inputs if not already provided via `$ARGUMENTS`:
   - **Independent claims** to chart
   - **Product description** (technical architecture, features, specs)
   - **Web search results** (optional, or use web search tool if available)
   - **Patent specification** (optional, for claim construction context)
   - **Prosecution history** (optional)
4. Fill in the `{{PLACEHOLDER}}` values with the user's content
5. If web search is available, search for product technical documentation
6. Execute the prompt to generate the claim chart
7. Present the output to the user
