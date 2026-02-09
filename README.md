# Legal Plugins for Claude

Plugins that turn Claude into a specialist for lawyers to streamline their workflows. Built for [Claude Cowork](https://claude.com/product/cowork), also compatible with [Claude Code](https://claude.com/product/claude-code).

This repository is based on [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) and focuses specifically on legal workflows.

## Why Plugins

Cowork lets you set the goal and Claude delivers finished, professional work. Plugins let you go further: tell Claude how you like work done, which tools and data to pull from, how to handle critical workflows, and what slash commands to expose — so your team gets better and more consistent outcomes.

The legal plugins bundle the skills, connectors, slash commands, and sub-agents specifically designed for legal professionals. Out of the box, they give Claude a strong starting point for helping anyone in a legal role. The real power comes when you customize them for your firm or legal department — your tools, your terminology, your processes — so Claude works like it was built for your team.

**💡 Recommended:** Both plugins work best when connected to [IURA MCP](https://iura.io) — a legal knowledge base providing access to over 1.5 million Polish legal documents including court rulings, legislation, and tax interpretations. While the Polish plugin (`legal-pl`) has IURA MCP built-in, the English plugin (`legal-en`) can also benefit from IURA for Polish law research when needed.

## Plugins

| Plugin | How it helps | Key features |
|--------|-------------|--------------|
| **[legal-en](./legal-en)** | Review contracts, triage NDAs, navigate compliance, assess risk, prep for meetings, draft templated responses, and perform bulk document reviews. | English language, general international legal practice |
| **[legal-pl](./legal-pl)** | Przegląd umów, triaż NDA, compliance, ocena ryzyka, przygotowanie spotkań, szablony odpowiedzi, masowy przegląd dokumentów. | Polish language, Polish law (KC, KSH, RODO, UZNK), **IURA MCP integration** with 1.5M+ Polish legal documents |
| **[legal-nl](./legal-nl)** | Beoordeel contracten, triageer NDA's, navigeer compliance, beoordeel risico, bereid vergaderingen voor, maak gestandaardiseerde antwoorden en voer bulk documentbeoordelingen uit. | Dutch language, Dutch law (Burgerlijk Wetboek, AVG/GDPR, AP) |

### IURA MCP Integration

**Both plugins work best with IURA MCP** — a legal knowledge base providing access to over 1.5 million Polish legal documents. The Polish plugin (`legal-pl`) has IURA MCP pre-configured, while the English plugin (`legal-en`) can be enhanced by adding IURA MCP to its `.mcp.json` for Polish law research.

[IURA MCP](https://iura.dev) provides access to:

- **Orzecznictwo sądów powszechnych** — common court rulings (Search_SP)
- **Orzecznictwo Sądu Najwyższego** — Supreme Court rulings (Search_SN)
- **Orzecznictwo NSA/WSA** — administrative court rulings (Search_CBOSA)
- **Trybunał Konstytucyjny** — Constitutional Tribunal rulings (Search_TK)
- **Krajowa Izba Odwoławcza** — public procurement rulings (Search_KIO)
- **Dziennik Ustaw** — legislation in force (Search_DU)
- **Interpretacje podatkowe** — tax interpretations (Search_IP)
- **Aktualności prawne** — legal news (Search_News)

**In `legal-pl`:** Every skill proactively uses IURA to verify current law, find precedents, and cite sources with case signatures and legal references.

**In `legal-en`:** Add IURA MCP to enable Polish law research when reviewing contracts with Polish governing law or working with Polish counterparties.

## Getting Started

### Cowork

Install plugins from [claude.com/plugins](https://claude.com/plugins/).

### Claude Code

```bash
# Add the marketplace first
claude plugin marketplace add iura-ai/iura-plugins

# Install the English legal plugin
claude plugin install legal-en@iura-plugins

# Or install the Polish legal plugin (includes IURA MCP)
claude plugin install legal-pl@iura-plugins

# Or install the Dutch legal plugin
claude plugin install legal-nl@iura-plugins
```

**💡 For best results:** Connect [IURA MCP](https://iura.dev) to enable real-time legal research. The Polish plugin includes IURA by default. For the English plugin, add IURA MCP to `.mcp.json` to enable Polish law research capabilities.

Once installed, the plugin activates automatically. Skills fire when relevant, and slash commands are available in your session (e.g., `/legal:review-contract`, `/legal:triage-nda`).

## How Plugins Work

Every plugin follows the same structure:

```
plugin-name/
├── .claude-plugin/plugin.json   # Manifest
├── .mcp.json                    # Tool connections
├── commands/                    # Slash commands you invoke explicitly
└── skills/                      # Domain knowledge Claude draws on automatically
```

- **Skills** encode the domain expertise, best practices, and step-by-step workflows Claude needs to give you useful help. Claude draws on them automatically when relevant.
- **Commands** are explicit actions you trigger (e.g., `/legal:review-contract`, `/legal:triage-nda`).
- **Connectors** wire Claude to the external tools your role depends on — document storage, chat, legal databases, and more — via [MCP servers](https://modelcontextprotocol.io/).

Every component is file-based — markdown and JSON, no code, no infrastructure, no build steps.

## Skills Overview

Both plugins include the following skills:

| Skill | Description |
|-------|-------------|
| `contract-review` | Playbook-based contract analysis, deviation classification, redline generation |
| `nda-triage` | NDA screening criteria, classification rules, routing recommendations |
| `compliance` | Privacy regulations, DPA review, data subject requests |
| `canned-responses` | Template management, response categories, escalation triggers |
| `legal-risk-assessment` | Risk severity framework, classification levels, escalation criteria |
| `meeting-briefing` | Meeting prep methodology, context gathering, action item tracking |
| `tabular-review` | Bulk document review into structured Excel spreadsheets |

The Polish plugin (legal-pl) enhances each skill with IURA MCP integration for real-time legal research.

## Making It Yours

The legal plugins are starting points. They become much more useful when you customize them for how your firm or legal department actually works:

- **Connect IURA MCP** — Add IURA MCP to `.mcp.json` for real-time access to Polish legal databases (court rulings, legislation, tax interpretations). Essential for Polish law work, highly recommended for international practice.
- **Swap connectors** — Edit `.mcp.json` to point at your specific tool stack.
- **Add firm context** — Drop your terminology, org structure, and processes into skill files so Claude understands your world.
- **Adjust workflows** — Modify skill instructions to match how your team actually does things, not how a textbook says to.
- **Configure your playbook** — Create a `legal.local.md` file with your organization's standard contract positions, risk tolerances, and negotiation strategies.

As your team customizes and shares plugins, Claude becomes a legal expert tailored to your organization. The context you define gets baked into every relevant interaction, so legal teams can spend less time on routine tasks and more time on strategic work.

## Contributing

Plugins are just markdown files. Fork the repo, make your changes, and submit a PR.
