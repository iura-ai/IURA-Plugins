# Connectors

## Connector for this Plugin

| Category | Connector | URL | Description |
|----------|-----------|-----|-------------|
| Legal knowledge base | IURA MCP | `https://mcp.iura.io/nl` | Dutch case law from Rechtbanken, Gerechtshoven, and Hoge Raad — over 1 million Dutch legal documents |

## IURA MCP (NL)

IURA MCP provides access to Dutch legal databases. For a detailed description of tools and parameters, see the `iura` skill (`skills/iura/SKILL.md`).

Available databases:
- Dutch court rulings (Rechtbanken, Gerechtshoven, Hoge Raad) via `Search_GU`
- Full text of rulings via `Read_Document`

### Available Tools

| Tool | Description | Key Parameters |
|------|-------------|----------------|
| `Search_GU` | Search Dutch case law | `query` (required), `context`, `top_k`, `date_from`, `date_to` |
| `Read_Document` | Read full text of a ruling | `document_id` (required), `query` (search mode), `start_chunk`/`end_chunk` (read mode) |
