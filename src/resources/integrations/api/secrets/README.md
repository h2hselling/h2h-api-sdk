# integrations.api.secrets

## Module Functions

### Delete an API secret <a name="delete"></a>

**API Endpoint**: `DELETE /integrations/api/{id}/secrets/{secretId}`

#### Parameters

| Parameter  | Required | Description | Example    |
| ---------- | :------: | ----------- | ---------- |
| `id`       |    ✓     |             | `"string"` |
| `secretId` |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.secrets.delete({
  id: "string",
  secretId: "string",
});
```

#### Response

##### Type

[IntegrationsApiSecretsDeleteResponse](/src/types/integrations-api-secrets-delete-response.ts)

##### Example

```typescript
{}
```

### Get all API secrets for an API integration <a name="list"></a>

**API Endpoint**: `GET /integrations/api/{id}/secrets`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.secrets.list({ id: "string" });
```

#### Response

##### Type

Array of [IntegrationsApiSecretsListResponseItem](/src/types/integrations-api-secrets-list-response-item.ts)

##### Example

```typescript
[{"apiId": "string", "createdAt": "string", "header": "string", "id": "string", "name": "string"}]
```

### Create a new API secret <a name="create"></a>

**API Endpoint**: `POST /integrations/api/{id}/secrets`

#### Parameters

| Parameter   | Required | Description | Example                                     |
| ----------- | :------: | ----------- | ------------------------------------------- |
| `id`        |    ✓     |             | `"string"`                                  |
| `data`      |    ✗     |             | `{"header": "x-api-key", "name": "string"}` |
| `└─ header` |    ✗     |             | `"x-api-key"`                               |
| `└─ name`   |    ✓     |             | `"string"`                                  |
| `└─ value`  |    ✗     |             | `"string"`                                  |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.integrations.api.secrets.create({ id: "string" });
```

#### Response

##### Type

[IntegrationsApiSecretsCreateResponse](/src/types/integrations-api-secrets-create-response.ts)

##### Example

```typescript
{"apiId": "string", "createdAt": "string", "header": "string", "id": "string", "name": "string"}
```
