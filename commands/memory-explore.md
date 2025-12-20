---
description: Deep exploration of the Forgetful knowledge graph
allowed-tools: mcp__forgetful__discover_forgetful_tools, mcp__forgetful__how_to_use_forgetful_tool, mcp__forgetful__execute_forgetful_tool
---

# Memory Explore

Perform deep knowledge graph traversal starting from a semantic query.

**Query**: $ARGUMENTS

## Traversal Phases

Execute these phases sequentially, tracking visited IDs to prevent cycles:

### Phase 1: Semantic Search
```
execute_forgetful_tool("query_memory", {
  "query": "<user's query>",
  "query_context": "Deep exploration via /memory-explore command",
  "k": 5,
  "include_links": true,
  "max_links_per_primary": 5
})
```

Collect all `primary_memories` and `linked_memories`.

### Phase 2: Expand Memory Details
For each primary memory, get full details:
```
execute_forgetful_tool("get_memory", {"memory_id": <id>})
```

Extract and collect:
- `linked_memory_ids` (additional memory connections)
- `document_ids` (linked documents)
- `code_artifact_ids` (linked code)
- `project_ids` (project associations)

### Phase 3: Entity Discovery
Find entities in the discovered projects:
```
execute_forgetful_tool("list_entities", {
  "project_ids": [<discovered project ids>]
})
```

### Phase 4: Entity Relationships
For each discovered entity, get relationship graph:
```
execute_forgetful_tool("get_entity_relationships", {
  "entity_id": <id>,
  "direction": "both"
})
```

### Phase 5: Entity-Linked Memories
For each entity, find all linked memories:
```
execute_forgetful_tool("get_entity_memories", {
  "entity_id": <id>
})
```

This returns `{"memory_ids": [...], "count": N}` - fetch any new memories not already visited.

## Response Format

Present results as a knowledge graph:

### Memories Found
List memories grouped by discovery phase:
- **Primary** (from semantic search)
- **Linked** (1-hop connections)
- **Entity-linked** (via entity associations)

For each memory show: Title, importance, tags, brief content snippet.

### Entities Discovered
List entities with their types and relationships:
- Entity name (type)
- Relationships: "works_for → Organization", "owns → Device", etc.
- Memory count linked to this entity

### Documents & Artifacts
If found, list linked reference materials:
- Document titles with types
- Code artifact titles with languages

### Graph Summary
Provide a brief summary:
- Total nodes discovered (memories + entities + docs + artifacts)
- Key clusters or themes identified
- Suggested follow-up queries for deeper exploration

## Example Output

```
## Knowledge Graph: "authentication patterns"

### Memories (12 total)
**Primary (5):**
- FastAPI JWT Authentication (importance: 9) - JWT middleware using httponly cookies...
- OAuth2 Decision (importance: 8) - Chose OAuth2 over API keys...
...

**Linked (5):**
- Session Management (importance: 7) - Redis-backed session storage...
...

**Entity-linked (2):**
- Security Review Notes (importance: 8) - From Sarah Chen's security audit...

### Entities (3)
- Sarah Chen (Individual) - 4 linked memories
  → works_for → Engineering Team
- Engineering Team (Team) - 8 linked memories
- Auth Service (Device) - 2 linked memories

### Graph Summary
12 memories, 3 entities, 0 documents, 1 code artifact
Key theme: JWT-based auth with Redis sessions
Suggested: /memory-explore "security audit findings"
```
