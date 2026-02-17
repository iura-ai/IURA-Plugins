# IURA Plugins for Claude

Open-source plugins that turn Claude into a legal specialist for legal professionals. Works best with [Claude Cowork](https://claude.com/product/cowork), also compatible with [Claude Code](https://claude.com/product/claude-code).

The plugins work standalone — contract review, NDA triage, NDA generation, and bulk document review are fully functional without any external services. Each skill encodes deep domain expertise in Polish (and soon Dutch) law: negotiation playbooks, risk classification, citation standards, and professional output formats.

## Why IURA MCP?

AI models hallucinate legal citations. They invent case law signatures, cite outdated statutes, and fabricate court rulings that don't exist. For casual use this is tolerable, but for legal work it's a dealbreaker.

[IURA MCP](https://iura.io) solves this by connecting Claude to 1.5M+ verified Polish legal documents in real time. With IURA MCP connected, your analysis includes:

- **Real case law citations** — verified signatures from Supreme Court, common courts, administrative courts, Constitutional Tribunal, and KIO
- **Current legislation** — actual text of statutes as in force today, not from training data
- **Divergent case law lines** — present both sides of a legal debate with real citations
- **Tax interpretations** — official positions from tax authorities with full signatures

The plugins are great standalone. With IURA MCP, they're complete.

## Plugins

| Plugin | Description | Status |
|--------|-------------|--------|
| **[iura-pl](./iura-pl)** | Polish legal workflows: contract review, NDA triage, NDA generation, legal memos, bulk document review. | Active |
| **[iura-nl](./iura-nl)** | Dutch legal workflows. | In preparation |

## Getting Started

### Cowork

Install plugins from [claude.com/plugins](https://claude.com/plugins/).

### Claude Code

```bash
# Add the marketplace
claude plugin marketplace add iura-ai/iura-plugins

# Install the Polish plugin (includes IURA MCP)
claude plugin install iura-pl@iura-plugins

# Install the Dutch plugin (in preparation)
claude plugin install iura-nl@iura-plugins
```

Once installed, the plugin activates automatically. Skills fire when relevant, and slash commands are available in your session.

## Skills Overview

### iura-pl

| Skill | Description |
|-------|-------------|
| `iura` | Legal research with IURA MCP — search strategy, citation standards, methodology |
| `contract-review` | Playbook-based contract analysis, deviation classification, redline generation |
| `nda-triage` | NDA screening criteria, classification rules, routing recommendations |
| `nda-generation` | NDA draft generation in Word format with entity data lookup |
| `legal-memo` | Legal memorandum drafting — IRAC analysis, case law citations, risk assessment |
| `tabular-review` | Bulk document review into structured Excel spreadsheets |

### Commands (iura-pl)

| Command | Description |
|---------|-------------|
| `/review-contract` | Review a contract against negotiation playbook |
| `/triage-nda` | Triage an incoming NDA |
| `/generate-nda` | Generate an NDA draft in Word format |
| `/legal-memo` | Draft a legal memorandum with analysis and recommendations |
| `/tabular-review` | Bulk-review documents into Excel |

## How Plugins Work

```
plugin-name/
├── .claude-plugin/plugin.json   # Manifest
├── .mcp.json                    # Tool connections (IURA MCP)
├── commands/                    # Slash commands you invoke explicitly
└── skills/                      # Domain knowledge Claude draws on automatically
```

- **Skills** encode domain expertise and workflows Claude draws on automatically.
- **Commands** are explicit actions you trigger (e.g., `/review-contract`).
- **Connectors** wire Claude to external tools via [MCP servers](https://modelcontextprotocol.io/).

## Making It Yours

The plugins are starting points. Customize them for your organization:

- **Configure your playbook** — Create `iura.local.md` with your standard contract positions, risk tolerances, and negotiation strategies.
- **Adjust workflows** — Modify skill instructions to match how your team works.
- **Add firm context** — Drop your terminology and processes into skill files.

## Contributing

Plugins are markdown and JSON files. Fork the repo, make your changes, and submit a PR.

## Support

If you find these plugins useful, give us a ⭐ on GitHub — it helps others discover the project.

Thinking about building custom skills for your law firm or legal department? We'd love to help. Reach out at [iura.io](https://iura.io).
