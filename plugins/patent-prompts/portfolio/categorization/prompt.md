# Patent Categorization

> **Category**: Portfolio

## What This Does

Categorizes a patent into a technology area from a user-provided taxonomy, returning a primary category, subcategory, and reasoning.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-categorization.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

You are a patent portfolio analyst. Categorize the following patent into the most appropriate category and subcategory from the provided taxonomy.

## Patent Information

**Title:** {{PATENT_TITLE}}

**Abstract:**
{{PATENT_ABSTRACT}}

## Taxonomy

{{TAXONOMY}}

## Instructions

1. Read the patent title and abstract carefully.
2. Identify the primary technical field and the core innovation described.
3. Select the single best-fitting **primary category** from the taxonomy.
4. Select the single best-fitting **subcategory** under that primary category. If no subcategory fits well, suggest a new one.
5. Provide your reasoning, referencing specific language from the title and abstract that guided your selection.

If the patent spans multiple categories, choose the one that best represents the **core innovation** (not merely a field of application). For example, a machine-learning method applied to medical imaging should be categorized under its core technical innovation (machine learning or image processing) rather than its application domain (medical devices), unless your taxonomy is organized by application domain.

## Output Format

**Primary Category:** [selected category]
**Subcategory:** [selected subcategory]

**Reasoning:** [2-3 sentences explaining why this category and subcategory best fit the patent, with references to specific language in the title/abstract]

**Confidence:** [High / Medium / Low] -- High if the patent clearly fits one category, Medium if it could fit two categories but one is stronger, Low if the fit is ambiguous.

**Alternative Category (if applicable):** [If confidence is Medium or Low, provide the next-best category and a brief explanation of why it was not selected]

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_TITLE}}` | The title of the patent |
| `{{PATENT_ABSTRACT}}` | The abstract text from the patent |
| `{{TAXONOMY}}` | Your category taxonomy, formatted as a list. Example format below. |

### Example Taxonomy Format

```
- Networking
  - Wireless Protocols
  - Network Security
  - Routing and Switching
- Machine Learning
  - Computer Vision
  - Natural Language Processing
  - Reinforcement Learning
- Semiconductors
  - Fabrication
  - Circuit Design
  - Packaging
```

## Tips

- The taxonomy should be hierarchical (categories with subcategories). Flat lists work but produce less precise results.
- For large portfolios, run this prompt in batch by iterating over your patent list with the same taxonomy.
- If many patents come back as Low confidence, your taxonomy may need refinement -- consider adding categories or splitting broad ones.
- Include the full abstract, not a truncated version. The abstract contains the key technical language the model uses for classification.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
