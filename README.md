![Forgetful Claude Code Plugin](/docs/images/hero_banner.png)

This plugin integrates [Forgetful AI Memory](https://github.com/ScottRBK/forgetful) with Claude Code - a semantic memory system using Zettelkasten principles.

## Quick Start

1. Install the plugin:
```bash
/plugin marketplace add ScottRBK/forgetful-plugin
```

2. Run setup:
```bash
/forgetful-setup
```

The setup command will configure Forgetful MCP in your global `~/.claude.json` - this persists across plugin updates.

**Standard setup** uses `uvx forgetful-ai` with SQLite storage (zero config, works immediately).

**Custom setup** guides you through advanced options: remote HTTP server, PostgreSQL, custom embeddings, etc. See [Forgetful Configuration](https://github.com/ScottRBK/forgetful/blob/main/docs/configuration.md) for details.

## What's Included

**Commands:**
- `/forgetful-setup` - Configure Forgetful MCP server (run after install)
- `/memory-search` - Semantic search across memories
- `/memory-save` - Create atomic memories with curation
- `/memory-list` - Browse recent memories
- `/memory-explore` - Deep knowledge graph traversal
- `/encode-repo` - Bootstrap a repository into the knowledge base

**Skills:**
- `using-forgetful-memory` - Guidance on when to query vs create, atomic memory principles
- `curating-memories` - Workflows for updating, linking, and marking memories obsolete
- `exploring-knowledge-graph` - Deep graph traversal across memories, entities, and relationships
