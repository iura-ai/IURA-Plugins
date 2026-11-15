# Connectors

## Connector for this Plugin

| Category | Connector | URL | Description |
|----------|-----------|-----|-------------|
| Legal knowledge base | IURA MCP | `https://mcp.iura.io/se/mcp` | Swedish legislation (SFS) and case law of the Swedish supreme, appellate and specialised courts |

## IURA MCP (SE)

For a detailed description of the tools, parameters and search strategy, see the `iura` skill (`skills/iura/SKILL.md`).

### Available Tools

| Tool | Description | Key Parameters |
|------|-------------|----------------|
| `search_swedish_legislation` | Search Swedish legislation (SFS), current or historical wording | `query` (required), `in_force_as_of` (required, YYYY-MM-DD), `context`, `top_k` |
| `search_swedish_supreme_court_rulings` | Högsta domstolen (civil and criminal cases) | `query` (required), `context`, `top_k`, `date_from`, `date_to` |
| `search_swedish_supreme_administrative_court_rulings` | Högsta förvaltningsdomstolen / Regeringsrätten | same |
| `search_swedish_court_of_appeal_rulings` | Hovrätterna | same |
| `search_swedish_administrative_court_of_appeal_rulings` | Kammarrätterna | same |
| `search_swedish_labour_court_rulings` | Arbetsdomstolen | same |
| `search_swedish_migration_court_of_appeal_rulings` | Migrationsöverdomstolen | same |
| `search_swedish_land_and_environment_court_of_appeal_rulings` | Mark- och miljööverdomstolen | same |
| `search_swedish_patent_and_market_court_of_appeal_rulings` | Patent- och marknadsöverdomstolen (with the Land and Environment Court and the Court of Patent Appeals) | same |
| `read_legal_document` | Read the full text of a ruling or act | `document_id` (required), `query` or `start_chunk`/`end_chunk` |
| `find_ruling_by_case_number` | Look up a ruling by case number or NJA reference | `signature` (required) |
| `search_web` | Current developments, förarbeten, authority guidance | `query` (required), `num_results` |

Queries to the Swedish tools are written in Swedish.
