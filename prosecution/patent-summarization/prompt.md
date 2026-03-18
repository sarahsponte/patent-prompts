# Patent Summarization

> **Category**: Prosecution

## What This Does

Generates a concise 2-3 paragraph summary of a patent based on its claims, highlighting the novel concepts and benefits in bold.

## How to Use

1. Copy the prompt below
2. Replace all `{{PLACEHOLDER}}` values with your content
3. Paste into your LLM

**Or try it now:** [Copy a pre-filled example](../../examples/try-patent-summarization.md) using our sample data and paste it directly into any LLM.

## The Prompt

---

Patent:

Title: {{PATENT_TITLE}}

Abstract: {{PATENT_ABSTRACT}}

Claims:
{{PATENT_CLAIMS}}

Return a 2-3 paragraph summary of the patent based on the claims. Bold (using markdown) the novel concepts and benefits. Do not include header text.

---

## Placeholders

| Placeholder | What to Put Here |
|---|---|
| `{{PATENT_TITLE}}` | The title of the patent |
| `{{PATENT_ABSTRACT}}` | The abstract text from the patent |
| `{{PATENT_CLAIMS}}` | The full claims text (all claims, or at minimum the independent claims) |

## Tips

- For best results, include all claims rather than just independent claims -- dependent claims often contain the most specific novel features.
- The output uses markdown bold formatting, so paste the result into a markdown-capable viewer for best readability.
- If the summary is too generic, try providing only the independent claims plus the most technically detailed dependent claims.

## Try It

Test this prompt using the sample data in [`../../examples/sample-patent.md`](../../examples/sample-patent.md).
