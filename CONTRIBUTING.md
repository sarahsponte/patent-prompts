# Contributing

We welcome contributions to improve these prompts and expand coverage to new workflows and jurisdictions.

## How to Contribute

1. **Fork** the repository
2. **Create a branch** for your changes
3. **Submit a pull request** with a clear description of what you changed and why

## What We're Looking For

- **Prompt improvements**: Better instructions, fewer hallucinations, more consistent output formatting
- **New prompts**: Additional patent workflows not currently covered
- **International contributions**: These prompts are currently US-centric (USPTO practice, 35 U.S.C. references). We'd welcome adaptations for EPO, CNIPA, JPO, KIPO, and other jurisdictions
- **Bug fixes**: Typos, broken links, incorrect placeholder references
- **Sample data**: Additional example patents or disclosures for testing

## Prompt Structure

Every prompt should follow this structure:

```
prompt-name/
  prompt.md       # The prompt with documentation
```

Each `prompt.md` should include:

1. **Header** with category
2. **What This Does** section
3. **How to Use** section
4. **The Prompt** (between `---` dividers)
5. **Placeholders** table
6. **Tips** section

## Guidelines

- Keep prompts self-contained. A user should be able to copy a single prompt, fill in placeholders, and get useful output.
- Use `{{PLACEHOLDER}}` format for all user inputs.
- Include anti-hallucination guardrails where the task involves factual claims (e.g., specification support, prior art citations).
- Test your prompt with at least one real or realistic example before submitting.
- If your prompt is jurisdiction-specific, note the jurisdiction clearly in the header and prompt text.

## Questions?

Open an issue if you have questions or want to discuss an idea before submitting a PR.
