# integrations.api

## Module Functions

### Delete an API integration <a name="delete"></a>

Delete an API integration by its ID.

**API Endpoint**: `DELETE /integrations/api/{id}`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.delete({ id: "string" });
```

#### Response

##### Type

[IntegrationsApiDeleteResponse](/src/types/integrations-api-delete-response.ts)

##### Example

```typescript
{}
```

### Get an API integration by ID <a name="get"></a>

Retrieve a single API integration by its ID.

**API Endpoint**: `GET /integrations/api/{id}`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.get({ id: "string" });
```

#### Response

##### Type

[IntegrationsApiGetResponse](/src/types/integrations-api-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string"}
```

### Create a new API integration <a name="create"></a>

Create a new API integration for the authenticated user.

**API Endpoint**: `POST /integrations/api`

#### Parameters

| Parameter        | Required | Description | Example                                   |
| ---------------- | :------: | ----------- | ----------------------------------------- |
| `data`           |    ✗     |             | `{"createdAt": "string", "id": "string"}` |
| `└─ accountId`   |    ✗     |             | `"string"`                                |
| `└─ baseUrl`     |    ✗     |             | `"string"`                                |
| `└─ createdAt`   |    ✓     |             | `"string"`                                |
| `└─ description` |    ✗     |             | `"string"`                                |
| `└─ id`          |    ✓     |             | `"string"`                                |
| `└─ name`        |    ✗     |             | `"string"`                                |
| `└─ userId`      |    ✗     |             | `"string"`                                |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.create();
```

#### Response

##### Type

[IntegrationsApiCreateResponse](/src/types/integrations-api-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string"}
```

## Submodules

- [operations](operations/README.md) - operations
- [secrets](secrets/README.md) - secrets
