# IURA Repository Plugin

AI plugin for working with your firm's **private document repository**, designed for [Cowork](https://claude.com/product/cowork) — also works in Claude Code.

Integrated with **IURA MCP** — unlike the jurisdiction plugins (`iura-pl`, `iura-nl`, `iura-eu`), which search public legal sources, this plugin connects Claude to *your own* documents: contracts, case files, correspondence, and anything else you upload to your IURA Repository. Documents are encrypted per-user; only the authenticated owner can read them.

> **Requires** an IURA account with an active MCP subscription and Repository access. Authentication is via OAuth — you'll be prompted to sign in on first use. If you also use a jurisdiction plugin, a single sign-in covers both.

## Tools

### Browse & read

| Tool | Description |
|------|-------------|
| `list_folders` | List the folders in your repository |
| `list_folder_docs` | List documents in a folder |
| `list_recent_documents` | Most recently added documents |
| `get_doc_metadata` | Document metadata (type, parties, dates, status) |
| `get_doc_one_pager` | One-page summary of a document |
| `list_doc_chunks` | List a document's chunks |
| `get_chunk_text` | Read a chunk with provenance |

### Search

| Tool | Description |
|------|-------------|
| `search_chunks_in_doc` | Semantic search within a single document |
| `search_chunks_in_folder` | Semantic search across a folder |

### Knowledge & workflow

| Tool | Description |
|------|-------------|
| `get_brain` | Your repository-wide knowledge map |
| `get_folder_card` | Compiled summary card for a folder |
| `add_folder_note` | Attach a note to a folder |
| `add_doc_annotation` | Annotate a document |
| `mark_doc_priority` | Flag a document's priority level |
| `track_open_question` | Track an open question about your matters |

## Installation

```bash
claude plugin marketplace add iura-ai/IURA-Plugins
claude plugin install iura-repo@iura-plugins
```

## License

Apache 2.0 — see [LICENSE](LICENSE). The plugin manifest is open source; the repository service itself is proprietary IURA infrastructure.
