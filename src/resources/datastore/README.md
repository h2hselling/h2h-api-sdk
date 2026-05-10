# datastore

## Module Functions

### List datastores <a name="list"></a>

List datastores owned by the authenticated user, optionally filtered by type or name search.

**API Endpoint**: `GET /datastore`

#### Parameters

| Parameter | Required | Description                                | Example               |
| --------- | :------: | ------------------------------------------ | --------------------- |
| `limit`   |    ✗     | Maximum number of results to return        | `123.0`               |
| `search`  |    ✗     | Substring match against the datastore name | `"string"`            |
| `type`    |    ✗     | Filter by datastore type                   | `"DATABASE_COLUMNAR"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.list();
```

#### Response

##### Type

Array of [DatastoreListResponseItem](/src/types/datastore-list-response-item.ts)

##### Example

```typescript
[{"createdAt": "string", "id": "string", "name": "string", "type": "DATABASE_COLUMNAR", "userId": "string"}]
```

### Get a datastore <a name="get"></a>

Retrieve a single datastore by its ID.

**API Endpoint**: `GET /datastore/{id}`

#### Parameters

| Parameter | Required | Description      | Example    |
| --------- | :------: | ---------------- | ---------- |
| `id`      |    ✓     | The datastore ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.get({ id: "string" });
```

#### Response

##### Type

[DatastoreGetResponse](/src/types/datastore-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "name": "string", "type": "DATABASE_COLUMNAR", "userId": "string"}
```

### Create a datastore <a name="create"></a>

Create a new datastore (FileStore, VectorStore, or Database).

**API Endpoint**: `POST /datastore`

#### Parameters

| Parameter              | Required | Description                                 | Example               |
| ---------------------- | :------: | ------------------------------------------- | --------------------- |
| `description`          |    ✓     | Description of the datastore                | `"string"`            |
| `name`                 |    ✓     | Name of the datastore                       | `"string"`            |
| `type`                 |    ✓     | The datastore type                          | `"DATABASE_COLUMNAR"` |
| `additionalProperties` |    ✗     |                                             | `{}`                  |
| `config`               |    ✗     | Optional config object                      | `{}`                  |
| `schema`               |    ✗     | JSON Schema (required for DATABASE_* types) | `{}`                  |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.create({
  description: "string",
  name: "string",
  type: "DATABASE_COLUMNAR",
});
```

#### Response

##### Type

[DatastoreCreateResponse](/src/types/datastore-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "name": "string", "type": "DATABASE_COLUMNAR", "userId": "string"}
```

## Submodules

- [items](items/README.md) - items
- [query](query/README.md) - query
