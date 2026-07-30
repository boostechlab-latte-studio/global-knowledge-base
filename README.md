# Global Knowledge Base

> **Current version:** see [`manifest.json`](manifest.json) for the exact published version/checksum consumers should use. See [`CHANGELOG.md`](CHANGELOG.md) for what changed in each version.

A centralized collection of structured knowledge content across multiple business and financial domains — written for reuse in documentation, retrieval-augmented generation (RAG) pipelines, and AI applications.

## Structure

Content is organized into topic categories. Each category is a folder; each file inside it is one self-contained topic, written for chunked retrieval rather than as a single long document.

```
├── analyst/       # Business analysis — profitability, liquidity, and margin
│                  # ratios for small-to-medium business owners, plus example
│                  # analytical conversation flows.
├── visualisasi/   # Choosing the right chart type and telling a clear story
│                  # from data — general-purpose, not limited to financial data.
└── manifest.json  # Version/package metadata for automated consumers.
```

More categories may be added over time (e.g. bookkeeping, tax obligations, operational SOPs) as content is written and validated.

## Content principles

- Each file is scoped to a single topic — one question, one formula, one concept.
- Content is written in plain, non-technical language for small business owners, not finance professionals.
- Numeric thresholds and interpretive guidance are validated against real test scenarios before being added.
- Sources are verified against official/authoritative references where one exists; where no single official standard exists (e.g. general business-ratio analysis), formulas are the universal mathematical definitions used across standard references.

## Versioning

`manifest.json` tracks the current published version, a checksum for the release package, and a download URL. Automated consumers should poll `manifest.json` for updates and verify the package checksum before use.

## License

Content in this repository is provided as-is for informational purposes. It does not constitute professional financial, legal, or accounting advice.
