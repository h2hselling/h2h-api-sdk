# datastore.query

## Module Functions

### Query a datastore <a name="create"></a>

Run a natural language query against a VectorStore, or a SQL query against a Database datastore.

**API Endpoint**: `POST /datastore/{id}/query`

#### Parameters

| Parameter                | Required | Description                                              | Example                 |
| ------------------------ | :------: | -------------------------------------------------------- | ----------------------- |
| `id`                     |    ✓     | The datastore ID                                         | `"string"`              |
| `query`                  |    ✓     | Natural-language query for VectorStore, SQL for Database | `"string"`              |
| `additionalProperties`   |    ✗     |                                                          | `{}`                    |
| `filters`                |    ✗     | Optional filters (VectorStore only)                      | `{}`                    |
| `└─ endDate`             |    ✗     |                                                          | `"1970-01-01T00:00:00"` |
| `└─ items`               |    ✗     |                                                          | `["string"]`            |
| `└─ similarityThreshold` |    ✗     |                                                          | `123.0`                 |
| `└─ startDate`           |    ✗     |                                                          | `"1970-01-01T00:00:00"` |
| `limit`                  |    ✗     | Maximum number of results (VectorStore only)             | `123.0`                 |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.query.create({
  query: "string",
  id: "string",
});
```

#### Response

##### Type

[DatastoreQueryCreateResponse](/src/types/datastore-query-create-response.ts)

##### Example

```typescript
{"data": "string"}
```
