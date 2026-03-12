# memory.tables.mutate

## Module Functions

### Mutate a memory table <a name="create"></a>

Execute a mutation (create, update, upsert, or delete) against a memory table.

**API Endpoint**: `POST /memory/tables/mutate`

#### Parameters

| Parameter              | Required | Description                                          | Example                          |
| ---------------------- | :------: | ---------------------------------------------------- | -------------------------------- |
| `mutation`             |    ✓     | The mutation to execute                              | `{"data": {}, "type": "create"}` |
| `└─ data`              |    ✓     | The data to insert, update, or upsert                | `{}`                             |
| `└─ type`              |    ✓     | The type of the mutation                             | `"create"`                       |
| `└─ where`             |    ✗     | The where clause to filter rows for update or delete | `{}`                             |
| `tableId`              |    ✓     | The ID of the memory table to mutate                 | `"string"`                       |
| `additionalProperties` |    ✗     |                                                      | `{}`                             |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.mutate.create({
  mutation: { data: {}, type: "create" },
  tableId: "string",
});
```

#### Response

##### Type

[MemoryTablesMutateCreateResponse](/src/types/memory-tables-mutate-create-response.ts)

##### Example

```typescript
{"count": 123.0}
```
