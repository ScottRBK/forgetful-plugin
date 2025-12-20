![Forgetful Claude Code Plugin](/docs/images/hero_banner.png)

This plugin integrates [Forgetful AI Memory](https://github.com/ScottRBK/forgetful) with Claude Code - a semantic memory system using Zettelkasten principles.

## Quick Start
Inside Claude Code
```bash
/plugin marketplace add ScottRBK/forgetful-plugin
```
### MCP Configuration

> **Required:** After installing, you must create an `.mcp.json` file from one of the examples below.

```bash
cd ~/.claude/plugins/forgetful-plugin
cp .mcp.json.stdio.example .mcp.json
```
Or for HTTP transport:
```bash 
cp .mcp.json.http.example .mcp.json
```

For any additional configuration you can also edit the `.mcp.json` and configure Forgetful as per the [Forgetful Configuration](https://github.com/ScottRBK/forgetful/blob/main/docs/configuration.md).

## What's Included

**Commands:**
- `/memory-search` - Semantic search across memories
- `/memory-save` - Create atomic memories with curation
- `/memory-list` - Browse recent memories
- `/encode-repo` - Bootstrap a repository into the knowledge base

**Skills:**
- `using-forgetful-memory` - Guidance on when to query vs create, atomic memory principles
- `curating-memories` - Workflows for updating, linking, and marking memories obsolete
