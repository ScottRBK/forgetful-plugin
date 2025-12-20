![Forgetful Claude Code Plugin](/hero_banner.png)

This plugin integrates [Forgetful AI Memory](https://github.com/ScottRBK/forgetful) with Claude Code - a semantic memory system using Zettelkasten principles.

## Quick Start

```bash
/plugin marketplace add ScottRBK/forgetful-plugin
/plugin install forgetful-plugin@forgetful-plugins
cd ~/.claude/plugins/forgetful-plugin
cp .mcp.json.stdio.example .mcp.json
```

Configure MCP as per the [Forgetful Configuration](https://github.com/ScottRBK/forgetful/blob/main/docs/configuration.md).

## What's Included

**Commands:**
- `/memory-search` - Semantic search across memories
- `/memory-save` - Create atomic memories with curation
- `/memory-list` - Browse recent memories
- `/encode-repo` - Bootstrap a repository into the knowledge base

**Skills:**
- `using-forgetful-memory` - Guidance on when to query vs create, atomic memory principles
- `curating-memories` - Workflows for updating, linking, and marking memories obsolete
