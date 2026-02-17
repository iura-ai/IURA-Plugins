# Contributing to IURA Plugins

Thank you for your interest in contributing to IURA Plugins! Whether it's a bug fix, a new skill, or an improvement to an existing one — we appreciate your help.

## How to Contribute

1. **Fork** the repository
2. **Create a branch** for your changes (`git checkout -b feature/my-new-skill`)
3. **Make your changes** following the guidelines below
4. **Submit a Pull Request** with a clear description of what you changed and why

## Reporting Bugs

Found a bug? [Open an issue](../../issues/new?template=bug-report.yml) using the Bug Report template. Please include:

- What you expected to happen
- What actually happened
- Steps to reproduce
- Which plugin and skill/command was involved

## Proposing New Skills

Have an idea for a new skill? [Open an issue](../../issues/new?template=new-skill-proposal.yml) using the New Skill Proposal template. We're especially interested in skills that:

- Address a real, recurring workflow for legal professionals
- Cover an area of law not yet represented
- Provide a meaningful "wow" factor over doing it manually

## Development Guidelines

### Project Structure

Each plugin follows this structure:

```
plugin-name/
├── .claude-plugin/plugin.json   # Plugin manifest
├── .mcp.json                    # MCP server connections
├── commands/                    # Slash commands (explicit workflows)
│   └── command-name.md
└── skills/                      # Domain knowledge (auto-activated)
    └── skill-name/SKILL.md
```

### Skills vs. Commands

- **Skills** (`skills/skill-name/SKILL.md`) — Domain knowledge that Claude draws on automatically. Contains rules, formats, standards, definitions. Think: *what to know*.
- **Commands** (`commands/command-name.md`) — Step-by-step workflows triggered by a slash command. Think: *what to do*.

A good feature usually has both: a command for the structured workflow and a skill for the deep domain knowledge.

### Language

- **iura-pl**: All skill and command content in Polish
- **iura-nl**: All skill and command content in Dutch
- **Root files** (README, CONTRIBUTING, etc.): English

### Style

- Markdown files, no frontmatter unless required by the plugin system
- Clear, imperative instructions in commands ("Do X", "Ask the user about Y")
- Descriptive, expert-level content in skills
- Reference other skills with: `przeczytaj SKILL.md skilla \`skill-name\``
- IURA MCP references should be conditional: "If IURA MCP is available... If not, note that citations require verification"

### Testing

Before submitting a PR, verify that:

- Skills activate correctly when relevant topics come up in conversation
- Commands produce the expected workflow when invoked
- Markdown renders properly
- Cross-references to other skills/commands are correct

## License

By contributing, you agree that your contributions will be licensed under the [Apache License 2.0](./LICENSE).
