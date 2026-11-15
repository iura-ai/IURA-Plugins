# Connectors

## Connector for this Plugin

| Category | Connector | URL | Description |
|----------|-----------|-----|-------------|
| Legal knowledge base | IURA MCP | `https://mcp.iura.io/be/mcp` | Belgian legislation (Justel) and case law (JUPORTAL, Constitutional Court, Council of State) |

## IURA MCP (BE)

For a detailed description of the tools, parameters and search strategy, see the `iura` skill (`skills/iura/SKILL.md`).

### Available Tools

| Tool | Description | Key Parameters |
|------|-------------|----------------|
| `search_belgian_legislation` | Search Belgian legislation (Justel), current or historical wording | `query` (required), `in_force_as_of` (required, YYYY-MM-DD), `context`, `top_k` |
| `search_belgian_case_law` | JUPORTAL: Court of Cassation, courts of appeal, labour courts and tribunals | `query` (required), `context`, `top_k`, `date_from`, `date_to` |
| `search_belgian_constitutional_court_rulings` | Constitutional Court (Grondwettelijk Hof / Cour constitutionnelle) | same |
| `search_belgian_council_of_state_rulings` | Council of State, administrative litigation section | same |
| `read_legal_document` | Read the full text of a ruling or act | `document_id` (required), `query` or `start_chunk`/`end_chunk` |
| `find_ruling_by_case_number` | Look up a ruling by ECLI, roll number or judgment number | `signature` (required) |
| `search_web` | Current developments, draft legislation, authority guidance | `query` (required), `num_results` |

Queries to the Belgian tools are written in French or Dutch.
