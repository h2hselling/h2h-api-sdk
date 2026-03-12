# memory.tables.query

## Module Functions

### Query a memory table <a name="create"></a>

Execute a data query against a memory table. Supports filtering, sorting, and pagination via query modifiers.

**API Endpoint**: `POST /memory/tables/query`

#### Parameters

| Parameter              | Required | Description                                           | Example    |
| ---------------------- | :------: | ----------------------------------------------------- | ---------- |
| `query`                |    ✓     | The data query to execute                             | `{}`       |
| `tableId`              |    ✓     | The ID of the memory table to query                   | `"string"` |
| `additionalProperties` |    ✗     |                                                       | `{}`       |
| `modifiers`            |    ✗     | Optional query modifiers (limit, offset, order, etc.) | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.query.create({
  query: {},
  tableId: "string",
});
```

#### Response

##### Type

[MemoryTablesQueryCreateResponse](/src/types/memory-tables-query-create-response.ts)

##### Example

```typescript
{"count": 123.0}
```
