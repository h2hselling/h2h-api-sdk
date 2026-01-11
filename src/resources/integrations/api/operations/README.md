# integrations.api.operations

## Module Functions

### Delete an API operation <a name="delete"></a>

**API Endpoint**: `DELETE /integrations/api/{id}/operations/{operationId}`

#### Parameters

| Parameter     | Required | Description | Example    |
| ------------- | :------: | ----------- | ---------- |
| `id`          |    ✓     |             | `"string"` |
| `operationId` |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.operations.delete({
  id: "string",
  operationId: "string",
});
```

#### Response

##### Type

[IntegrationsApiOperationsDeleteResponse](/src/types/integrations-api-operations-delete-response.ts)

##### Example

```typescript
{}
```

### Get an API operation by ID <a name="get"></a>

**API Endpoint**: `GET /integrations/api/{id}/operations/{operationId}`

#### Parameters

| Parameter     | Required | Description | Example    |
| ------------- | :------: | ----------- | ---------- |
| `id`          |    ✓     |             | `"string"` |
| `operationId` |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.operations.get({
  id: "string",
  operationId: "string",
});
```

#### Response

##### Type

[IntegrationsApiOperationsGetResponse](/src/types/integrations-api-operations-get-response.ts)

##### Example

```typescript
{"apiId": "string", "createdAt": "string", "id": "string", "method": "DELETE", "path": "string"}
```

### Update an API operation <a name="patch"></a>

**API Endpoint**: `PATCH /integrations/api/{id}/operations/{operationId}`

#### Parameters

| Parameter          | Required | Description | Example    |
| ------------------ | :------: | ----------- | ---------- |
| `id`               |    ✓     |             | `"string"` |
| `operationId`      |    ✓     |             | `"string"` |
| `data`             |    ✗     |             | `{}`       |
| `└─ method`        |    ✗     |             | `"DELETE"` |
| `└─ path`          |    ✗     |             | `"string"` |
| `└─ payloadSchema` |    ✗     |             | `{}`       |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.operations.patch({
  id: "string",
  operationId: "string",
});
```

#### Response

##### Type

[IntegrationsApiOperationsPatchResponse](/src/types/integrations-api-operations-patch-response.ts)

##### Example

```typescript
{"apiId": "string", "createdAt": "string", "id": "string", "method": "DELETE", "path": "string"}
```

### Create a new API operation <a name="create"></a>

**API Endpoint**: `POST /integrations/api/{id}/operations`

#### Parameters

| Parameter          | Required | Description | Example                                                    |
| ------------------ | :------: | ----------- | ---------------------------------------------------------- |
| `id`               |    ✓     |             | `"string"`                                                 |
| `data`             |    ✗     |             | `{"method": "DELETE", "name": "string", "path": "string"}` |
| `└─ method`        |    ✓     |             | `"DELETE"`                                                 |
| `└─ name`          |    ✓     |             | `"string"`                                                 |
| `└─ path`          |    ✓     |             | `"string"`                                                 |
| `└─ payloadSchema` |    ✗     |             | `{}`                                                       |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.operations.create({ id: "string" });
```

#### Response

##### Type

[IntegrationsApiOperationsCreateResponse](/src/types/integrations-api-operations-create-response.ts)

##### Example

```typescript
{"apiId": "string", "createdAt": "string", "id": "string", "method": "DELETE", "path": "string"}
```
