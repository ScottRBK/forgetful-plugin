![Forgetful Claude Code Plugin](/hero_banner.png)

This repository contains the configuration neccessary to install a [Claude Code Plugin](https://code.claude.com/docs/en/plugins-reference#plugin-manifest-schema) for the [Forgetful AI Memory MCP](https://github.com/ScottRBK/forgetful). 


## MCP

Ships with STDIO transport however if you are calling Forgetful via HTTP then you must change the `.mcp.json` file to ensure it connects to the correct version of forgetful.

```json
{
  "mcpServers": {
    "forgetful": {
      "type": "http",
      "url": "http://localhost:8020/mcp"
    }
  }
}
```
