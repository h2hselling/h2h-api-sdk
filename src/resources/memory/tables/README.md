# memory.tables

## Module Functions

### Delete a memory table <a name="delete"></a>

Delete a memory table and all its rows by the table ID.

**API Endpoint**: `DELETE /memory/tables/{id}`

#### Parameters

| Parameter | Required | Description         | Example    |
| --------- | :------: | ------------------- | ---------- |
| `id`      |    ✓     | The memory table ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.delete({ id: "string" });
```

#### Response

##### Type

[MemoryTablesDeleteResponse](/src/types/memory-tables-delete-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "schema": {}, "userId": "string"}
```

### List memory tables <a name="list"></a>

Retrieve a paginated list of memory tables owned by the authenticated user.

**API Endpoint**: `GET /memory/tables`

#### Parameters

| Parameter | Required | Description              | Example |
| --------- | :------: | ------------------------ | ------- |
| `limit`   |    ✗     | Number of items per page | `123.0` |
| `page`    |    ✗     | Page number (1-based)    | `123.0` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.list();
```

#### Response

##### Type

Array of [MemoryTablesListResponseItem](/src/types/memory-tables-list-response-item.ts)

##### Example

```typescript
[{"createdAt": "string", "description": "string", "id": "string", "name": "string", "schema": {}, "userId": "string"}]
```

### Get a memory table <a name="get"></a>

Retrieve a single memory table by its ID, including its schema definition.

**API Endpoint**: `GET /memory/tables/{id}`

#### Parameters

| Parameter | Required | Description         | Example    |
| --------- | :------: | ------------------- | ---------- |
| `id`      |    ✓     | The memory table ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.get({ id: "string" });
```

#### Response

##### Type

[MemoryTablesGetResponse](/src/types/memory-tables-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "schema": {}, "userId": "string"}
```

### Create a memory table <a name="create"></a>

Create a new memory table with a name, description, and JSON Schema defining its row structure.

**API Endpoint**: `POST /memory/tables`

#### Parameters

| Parameter              | Required | Description                                              | Example    |
| ---------------------- | :------: | -------------------------------------------------------- | ---------- |
| `description`          |    ✓     | Description of the memory table                          | `"string"` |
| `name`                 |    ✓     | Name of the memory table                                 | `"string"` |
| `schema`               |    ✓     | JSON Schema defining the structure of rows in this table | `{}`       |
| `additionalProperties` |    ✗     |                                                          | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.memory.tables.create({
  description: "string",
  name: "string",
  schema: {},
});
```

#### Response

##### Type

[MemoryTablesCreateResponse](/src/types/memory-tables-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "schema": {}, "userId": "string"}
```

## Submodules

- [mutate](mutate/README.md) - mutate
- [query](query/README.md) - query
