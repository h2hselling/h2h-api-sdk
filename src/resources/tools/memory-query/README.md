# tools.memory-query

## Module Functions

### Query memory <a name="create"></a>

Query or mutate a memory table using a single tool-oriented request format.

**API Endpoint**: `POST /tools/memory_query`

#### Parameters

| Parameter | Required | Description | Example                                                          |
| --------- | :------: | ----------- | ---------------------------------------------------------------- |
| `data`    |    ✓     |             | `{"input": {"query": {}}, "tableId": "string", "type": "QUERY"}` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.memoryQuery.create({
  data: { input: { query: {} }, tableId: "string", type: "QUERY" },
});
```

#### Response

##### Type

[ToolsMemoryQueryCreateResponse](/src/types/tools-memory-query-create-response.ts)

##### Example

```typescript
{"count": 123.0}
```
