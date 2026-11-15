# IURA Repository Plugin

AI plugin for working with your firm's **private document repository**, designed for [Cowork](https://claude.com/product/cowork) — also works in Claude Code.

Integrated with **IURA MCP** — unlike the jurisdiction plugins (`iura-pl`, `iura-nl`, `iura-eu`), which search public legal sources, this plugin connects Claude to *your own* documents: contracts, case files, correspondence, and anything else you upload to your IURA Repository. Documents are encrypted per-user; only the authenticated owner can read them.

> **Requires** an IURA account with an active MCP subscription and Repository access. Authentication is via OAuth — you'll be prompted to sign in on first use. If you also use a jurisdiction plugin, a single sign-in covers both.

## Tools

### Browse & read

| Tool | Description |
|------|-------------|
| `list_repository_folders` | List the folders in your repository |
| `list_repository_folder_documents` | List documents in a folder |
| `list_repository_recent_documents` | Most recently added documents |
| `get_repository_document_metadata` | Document metadata (type, parties, dates, status) |
| `get_repository_document_summary` | One-page summary of a document |
| `list_repository_document_sections` | List a document's chunks |
| `get_repository_section_text` | Read a chunk with provenance |
| `get_repository_document_links` | Links to open or download a document |

### Search

| Tool | Description |
|------|-------------|
| `search_repository_document` | Semantic search within a single document |
| `search_repository_folder` | Semantic search across a folder |

### Knowledge & workflow

| Tool | Description |
|------|-------------|
| `get_repository_overview` | Your repository-wide knowledge map |
| `get_repository_folder_overview` | Compiled summary card for a folder |
| `add_repository_folder_note` | Attach a note to a folder |
| `add_repository_document_annotation` | Annotate a document |
| `set_repository_document_priority` | Flag a document's priority level |
| `add_repository_open_question` | Track an open question about your matters |
| `open_repository_upload` | Open the document upload form |

## Installation

```bash
claude plugin marketplace add iura-ai/IURA-Plugins
claude plugin install iura-repo@iura-plugins
```

## License

Apache 2.0 — see [LICENSE](LICENSE). The plugin manifest is open source; the repository service itself is proprietary IURA infrastructure.
