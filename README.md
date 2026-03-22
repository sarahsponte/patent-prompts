# ArcPrime Patent Prompts

Hi, I'm Jon. I'm the founder of [ArcPrime](https://arcprime.com). Before this, I was patent counsel at Meta and Fish & Richardson. I've spent my career doing patent work end to end: drafting claims from disclosures, reviewing applications, searching prior art, responding to office actions, building claim charts, filing continuations, and making portfolio decisions across thousands of patents.

These prompts are how I actually do patent work. Drafting claims from a messy disclosure, figuring out which continuations to file, mapping claims to a competitor's product, deciding what to prune. These are real workflows I've run across real patents and real portfolios. They work for me.

They won't replace your judgment. A prompt can give you a strong first draft of claims, a solid prior art analysis, a continuation strategy worth discussing. But you still need to review, refine, and make the final call. The work's not done when the output lands. But a lot of it is, and you're starting from a much better place than a blank page.

**Two caveats:**

1. **Domain.** These prompts come from my practice, which is mostly software and hardware. If you work in pharma, biotech, or other fields, you'll want to adjust the claim drafting conventions and legal frameworks to match your domain.
2. **Depth.** These are the single-prompt versions, designed for easy use. In production at ArcPrime, these run as multi-stage pipelines with anti-hallucination checks, specification cross-referencing, and output validation. The multi-stage versions are where the last mile of accuracy comes from.

Fork them. Improve them. Make them yours.

**Who this is for:**

- **Patent attorneys and agents** who want to 100x their throughput on drafting, prosecution, and portfolio analysis
- **In-house patent counsel** making strategic decisions about large portfolios: pruning, continuations, categorization
- **Patent professionals** at any level who want to see what AI can actually do for patent work, with real prompts that produce real output

## Connect with Me

If you're in-house counsel applying AI to patent work, I run a WhatsApp group of 40+ practitioners sharing what works. Send me an email at [jon@arcprime.com](mailto:jon@arcprime.com) or connect with me on [LinkedIn](https://www.linkedin.com/in/jonathan-liu-6571563/) to join.

## Quick Start

1. Pick a prompt from the [Prompt Catalog](#prompt-catalog) below
2. Open the `prompt.md` file and copy the prompt
3. Replace all `{{PLACEHOLDER}}` values with your patent data
4. Paste into any capable LLM

**Want to see one in action first?** Every prompt has a **Try it** link, a pre-filled version using our [sample patent](examples/sample-patent.md) and [sample disclosure](examples/sample-disclosure.md). Just copy and paste into any LLM.

## Prompt Catalog

🌐 = requires [web search](#web-search) &nbsp;&nbsp; 🧪 = pre-filled example you can paste into any LLM

### Pre-Filing

| Prompt | Description | 🌐 | 🧪 |
|---|---|---|---|
| [Claims Drafting](pre-filing/claims-drafting/prompt.md) | Draft patent claims from an invention disclosure | | [🧪](examples/try-claims-drafting.md) |
| [Detectability Assessment](pre-filing/detectability-assessment/prompt.md) | Assess whether infringement of proposed claims can be detected | | [🧪](examples/try-detectability-assessment.md) |
| [Disclosure Questions](pre-filing/disclosure-questions/prompt.md) | Generate clarifying questions for an invention disclosure | | [🧪](examples/try-disclosure-questions.md) |
| [Draft Review](pre-filing/draft-review/prompt.md) | Review a patent application draft for common issues | | [🧪](examples/try-draft-review.md) |
| [Prior Art Analysis](pre-filing/prior-art-analysis/prompt.md) | Analyze independent claims against prior art | 🌐 | [🧪](examples/try-prior-art-analysis.md) |

### Prosecution

| Prompt | Description | 🌐 | 🧪 |
|---|---|---|---|
| [Patent Summarization](prosecution/patent-summarization/prompt.md) | Generate a concise summary of a patent from its claims | | [🧪](examples/try-patent-summarization.md) |
| [Concept Extraction](prosecution/concept-extraction/prompt.md) | Extract key technical concepts from a patent specification | | [🧪](examples/try-concept-extraction.md) |

### Portfolio

| Prompt | Description | 🌐 | 🧪 |
|---|---|---|---|
| [Continuation - Targeted](portfolio/continuation-targeted/prompt.md) | Draft continuation claims targeting a specific competitor product | 🌐 | [🧪](examples/try-continuation-targeted.md) |
| [Continuation - Broadened](portfolio/continuation-broadened/prompt.md) | Identify opportunities for broadened continuation claims | | [🧪](examples/try-continuation-broadened.md) |
| [Continuation - Unclaimed Subject Matter](portfolio/continuation-unclaimed/prompt.md) | Find disclosed but unclaimed subject matter for continuation claims | | [🧪](examples/try-continuation-unclaimed.md) |
| [Claim Chart](portfolio/claim-chart/prompt.md) | Map patent claims to product features for infringement analysis | 🌐 | [🧪](examples/try-claim-chart.md) |
| [Patent Categorization](portfolio/categorization/prompt.md) | Categorize a patent by technology area using a custom taxonomy | | [🧪](examples/try-categorization.md) |
| [Pruning Analysis](portfolio/pruning-analysis/prompt.md) | Evaluate whether a patent should be maintained or abandoned | | [🧪](examples/try-pruning-analysis.md) |

## Placeholder Convention

All prompts use `{{PLACEHOLDER}}` format for user inputs. Each prompt's documentation includes a table describing what to put in each placeholder. Common placeholders:

| Placeholder | Description |
|---|---|
| `{{PATENT_CLAIMS}}` | The full claims text of a patent |
| `{{PATENT_SPECIFICATION}}` | The detailed description / specification of a patent |
| `{{PATENT_TITLE}}` | The title of a patent |
| `{{PATENT_ABSTRACT}}` | The abstract of a patent |
| `{{PRODUCT_DESCRIPTION}}` | A description of a product for infringement analysis |

## Tips for Best Results

- **Use full text, not summaries.** These prompts work best with complete patent text (full claims, full specification). Truncated inputs produce lower-quality outputs.
- **More context is better.** When analyzing against a product, include technical specifications, architecture details, and documentation -- not just marketing copy.
- **Iterate.** Run the prompt, review the output, and re-run with adjustments. Consider modifying the product description or adding context the model missed.
- **Model selection.** These prompts work with any capable LLM. For complex tasks (claim drafting, claim charts), stronger models produce noticeably better results.
- **Verify everything.** LLM outputs are analytical aids, not final work product. Always have a qualified patent professional review the output.

## Web Search

Some prompts (marked with 🌐) work best when the LLM can search the internet — for example, to find prior art references or gather technical details about an accused product. If your LLM has built-in web search, it can search directly. Otherwise, paste your own search results into the `{{WEB_SEARCH_RESULTS}}` placeholder. Each prompt's documentation explains what to search for.

## Install as an AI Agent Skill

These prompts are available as installable skills for AI coding agents. Once installed, you can invoke them directly from your agent (e.g., `/patent-prompts:claims-drafting`).

### Claude Code

Install as a plugin:

```bash
/plugin install patent-prompts@arcprime-ip/patent-prompts
```

Or add manually to a project:

```bash
git clone https://github.com/arcprime-ip/patent-prompts.git
claude --plugin-dir ./patent-prompts
```

After installation, all prompts are available as slash commands:

| Skill | Command |
|---|---|
| Claims Drafting | `/patent-prompts:claims-drafting` |
| Detectability Assessment | `/patent-prompts:detectability-assessment` |
| Disclosure Questions | `/patent-prompts:disclosure-questions` |
| Draft Review (101 + 112) | `/patent-prompts:draft-review` |
| Draft Review (101 only) | `/patent-prompts:draft-review-101` |
| Draft Review (112 only) | `/patent-prompts:draft-review-112` |
| Prior Art Analysis | `/patent-prompts:prior-art-analysis` |
| Patent Summarization | `/patent-prompts:patent-summarization` |
| Concept Extraction | `/patent-prompts:concept-extraction` |
| Continuation - Targeted | `/patent-prompts:continuation-targeted` |
| Continuation - Broadened | `/patent-prompts:continuation-broadened` |
| Continuation - Unclaimed | `/patent-prompts:continuation-unclaimed` |
| Claim Chart | `/patent-prompts:claim-chart` |
| Patent Categorization | `/patent-prompts:categorization` |
| Pruning Analysis | `/patent-prompts:pruning-analysis` |

### OpenAI Codex CLI

Codex automatically reads the `AGENTS.md` file in this repository. Clone the repo into your project or working directory:

```bash
git clone https://github.com/arcprime-ip/patent-prompts.git
```

Then reference the prompts in your Codex sessions — Codex will use the `AGENTS.md` instructions to locate and apply the relevant prompt files.

### Other Agents (Cursor, Gemini CLI, etc.)

The `SKILL.md` format is an open standard supported by multiple agents. Clone the repo and point your agent at the `skills/` directory, or copy individual `SKILL.md` files into your agent's skills directory.

## Jurisdiction

These prompts are written for **US patent practice** (USPTO procedures, 35 U.S.C. references, MPEP conventions). Many of the underlying concepts transfer to other jurisdictions, but the specific legal frameworks, claim drafting conventions, and procedural references are US-centric.

We welcome contributions adapting these prompts for EPO, CNIPA, JPO, KIPO, and other patent offices. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to submit.

## Disclaimer

These prompts are provided for **educational and informational purposes only**. They do not constitute legal advice. Patent law is complex and jurisdiction-specific. Always consult a qualified patent attorney or agent before making decisions based on LLM-generated patent analysis. The authors and contributors are not responsible for any actions taken based on outputs generated using these prompts.

## License

MIT License. See [LICENSE](LICENSE) for details.
