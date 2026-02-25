# Declare AI 🔬

**An open standard for AI content disclosure.**

A universal "nutrition label" for the web — showing how AI contributed to any piece of content, in a single glance. Free, open source, and community governed.

---

## What is this?

As AI becomes embedded in the production of virtually all digital content, audiences, researchers, educators, and regulators have no standardized way to understand the provenance of what they read, watch, or hear.

**Declare AI** solves this with:

- A lightweight **`declare-ai.json` schema** any creator or platform can publish alongside their content
- An **embeddable JS widget** — a draggable pie chart icon that expands into a full disclosure card
- A **browser extension** that auto-detects declarations on any page
- A **self-declaration portal** where creators can generate and host their JSON file
- A **community forum** for disputes, corrections, and governance

Think Creative Commons licensing, but for AI contribution transparency.

---

## Live Demo

👉 **[View the interactive developer briefing](https://declare-ai.github.io/declare-ai/declare-ai-devteam.html)**

---

## The declare-ai.json Schema

Drop this file alongside any piece of content, or link to it from a `<meta>` tag:

```json
{
  "$schema": "https://declare-ai.org/schema/v1.json",
  "version": "1.0.0",
  "content_title": "My Article Title",
  "content_url": "https://example.com/my-article",
  "content_type": "article",
  "declared_by": "Author Name",
  "declared_at": "2025-09-14T10:30:00Z",
  "declaration_method": "self-declared",
  "contributions": [
    {
      "type": "writing",
      "pct": 55,
      "tool": "Claude 3.7 Sonnet",
      "provider": "Anthropic",
      "role": "First draft and editing",
      "human_hours": 1.5
    },
    {
      "type": "human",
      "pct": 45,
      "role": "Research, fact-checking, final edit",
      "human_hours": 3.0
    }
  ],
  "contributors": [
    { "name": "Author Name", "role": "Author" }
  ],
  "license": "CC-BY-4.0"
}
```

**Contribution types:** `writing` · `code` · `visual` · `audio` · `research` · `editing` · `human`

Full schema reference is in [`/schema`](./schema).

---

## Embed the Widget

Add the Declare AI disclosure widget to any webpage with one line:

```html
<script src="https://cdn.declare-ai.org/widget/v1.js" data-declaration="/declare-ai.json"></script>
```

A small interactive pie chart icon appears on the page. Visitors can click it to see the full AI contribution breakdown — collapsible, draggable, zero dependencies, ~8kb.

---

## Repository Structure

```
declare-ai/
├── schema/          # JSON Schema definition and validator
├── widget/          # Embeddable JS widget (vanilla, zero deps)
├── extension/       # Browser extension (Chrome/Firefox/Safari)
├── api/             # Backend REST API (Node.js + Fastify)
├── site/            # declare-ai.org website (Next.js)
├── docs/            # Documentation and RFC archive
└── declare-ai-devteam.html   # Interactive prototype demo
```

---

## Project Status

| Component | Status |
|-----------|--------|
| Schema v1.0 draft | ✅ Ready for RFC feedback |
| Widget prototype | ✅ Interactive demo live |
| Schema validator | 🔲 Help wanted |
| REST API | 🔲 Help wanted |
| Browser extension | 🔲 Help wanted |
| Declaration portal | 🔲 Help wanted |
| Discourse forum | 🔲 Help wanted |

---

## Contributing

This project is in its earliest stage — the best time to have real influence over the direction of an open standard.

**Good first contributions:**
- Review the [schema draft](./schema) and open an Issue with feedback
- Build the JSON schema validator
- Port the widget prototype to a proper NPM package
- Write documentation

**To get started:**
1. Read the [interactive briefing](https://declare-ai.github.io/declare-ai/declare-ai-devteam.html) to understand the full vision
2. Browse [open Issues](../../issues) for tasks tagged `good first issue`
3. Join the discussion in [GitHub Discussions](../../discussions)
4. Open a PR — all contributors credited in CONTRIBUTORS.md

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before submitting your first PR.

---

## Use Cases

- 🏫 **Education** — Academic integrity, student work disclosure, AI-assisted textbooks
- 🔬 **Research & Science** — Journal submissions, preprint provenance, data attribution
- 📰 **Journalism** — News article transparency, editorial policy compliance
- 🎨 **Art & Creative** — Artist process disclosure, authorship conversations
- ⚖️ **Legal & Regulatory** — EU AI Act compliance layer, platform policy tool
- 💊 **Medicine** — Health content trust scoring, clinical content provenance

---

## Roadmap

| Phase | Target | Milestone |
|-------|--------|-----------|
| 0 | ✅ Now | Schema draft, interactive demo, dev briefing |
| 1 | Weeks 1–6 | Schema validator, declaration form, NPM widget |
| 2 | Weeks 6–14 | REST API, CDN hosting, browser extension MVP |
| 3 | Months 4–6 | Accounts, dispute system, community forum |
| 4 | Months 6–12 | Scoring engine, CMS plugins, Firefox/Safari ext |
| 5 | Year 2+ | W3C proposal, platform partnerships |

---

## License

MIT — free to use, embed, fork, and redistribute without restriction.

This standard is designed to be universally adoptable. No lock-in, no fees, no tracking.

---

## Acknowledgements

Conceived and originated by **BetterToBest**, gifted to the internet as an open standard.  
Built with the assistance of Claude (Anthropic).

---

*If this project matters to you — star it, share it, or open an issue. That's how open standards begin.*
