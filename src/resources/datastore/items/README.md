# datastore.items

## Module Functions

### Delete a datastore item <a name="delete"></a>

Delete a datastore item and its underlying storage objects.

**API Endpoint**: `DELETE /datastore/items/{item_id}`

#### Parameters

| Parameter | Required | Description           | Example    |
| --------- | :------: | --------------------- | ---------- |
| `itemId`  |    ✓     | The datastore item ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.items.delete({ itemId: "string" });
```

#### Response

##### Type

[DatastoreItemsDeleteResponse](/src/types/datastore-items-delete-response.ts)

##### Example

```typescript
{"createdAt": "string", "datastoreId": "string", "id": "string", "name": "string"}
```

### Get a datastore item <a name="get"></a>

Retrieve a datastore item, including its raw data (FileStore returns base64-encoded bytes for binary content).

**API Endpoint**: `GET /datastore/items/{item_id}`

#### Parameters

| Parameter | Required | Description           | Example    |
| --------- | :------: | --------------------- | ---------- |
| `itemId`  |    ✓     | The datastore item ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.items.get({ itemId: "string" });
```

#### Response

##### Type

[DatastoreItemsGetResponse](/src/types/datastore-items-get-response.ts)

##### Example

```typescript
{"data": "string", "encoding": "base64"}
```

### List datastore items <a name="list"></a>

List datastore items at the given prefix. Returns S3-style entries: nested prefixes (folders) and items at the prefix level.

**API Endpoint**: `GET /datastore/{id}/items`

#### Parameters

| Parameter | Required | Description                   | Example    |
| --------- | :------: | ----------------------------- | ---------- |
| `id`      |    ✓     | The datastore ID              | `"string"` |
| `prefix`  |    ✗     | The path prefix to list under | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.items.list({ id: "string" });
```

#### Response

##### Type

Union of[DatastoreItemsListResponseItemObj0](/src/types/datastore-items-list-response-item-obj0.ts), [DatastoreItemsListResponseItemObj1](/src/types/datastore-items-list-response-item-obj1.ts)

##### Example

```typescript
[{"name": "string", "path": "string", "type": "prefix"}]
```

### Create a datastore item <a name="create"></a>

Create a new item in a FileStore or VectorStore datastore. For VectorStores the data must be embeddable text.

**API Endpoint**: `POST /datastore/{id}/items`

#### Parameters

| Parameter              | Required | Description                                                                | Example      |
| ---------------------- | :------: | -------------------------------------------------------------------------- | ------------ |
| `id`                   |    ✓     | The datastore ID                                                           | `"string"`   |
| `name`                 |    ✓     | Item name                                                                  | `"string"`   |
| `additionalProperties` |    ✗     |                                                                            | `{}`         |
| `data`                 |    ✗     | Item content (plain text by default)                                       | `"string"`   |
| `description`          |    ✗     | Optional description                                                       | `"string"`   |
| `encoding`             |    ✗     | Encoding of the `data` field. Use `base64` to upload binary data via JSON. | `"base64"`   |
| `mimeType`             |    ✗     | Override the inferred MIME type (filestore only)                           | `"string"`   |
| `path`                 |    ✗     | Path under which the item is stored                                        | `"string"`   |
| `tags`                 |    ✗     | Optional tags                                                              | `["string"]` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.datastore.items.create({
  name: "string",
  id: "string",
});
```

#### Response

##### Type

[DatastoreItemsCreateResponse](/src/types/datastore-items-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "datastoreId": "string", "id": "string", "name": "string"}
```
