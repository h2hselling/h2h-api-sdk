# workspace.variables

## Module Functions

### Delete a workspace variable <a name="delete"></a>

Delete a workspace variable by ID. If the variable is a secret, the encrypted value in S3 is also removed.

**API Endpoint**: `DELETE /workspace/variables`

#### Parameters

| Parameter | Required | Description | Example            |
| --------- | :------: | ----------- | ------------------ |
| `data`    |    ✗     |             | `{"id": "string"}` |
| `└─ id`   |    ✓     |             | `"string"`         |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workspace.variables.delete();
```

#### Response

##### Type

[WorkspaceVariablesDeleteResponse](/src/types/workspace-variables-delete-response.ts)

##### Example

```typescript
{}
```

### List workspace variables <a name="list"></a>

Retrieve a paginated list of workspace variables, optionally filtered by name, origin, or API.

**API Endpoint**: `GET /workspace/variables`

#### Parameters

| Parameter | Required | Description                           | Example    |
| --------- | :------: | ------------------------------------- | ---------- |
| `api`     |    ✗     | Filter by API ID                      | `"string"` |
| `limit`   |    ✗     |                                       | `123.0`    |
| `name`    |    ✗     | Filter by variable name (exact match) | `"string"` |
| `origin`  |    ✗     | Filter by origin ID                   | `"string"` |
| `page`    |    ✗     |                                       | `123.0`    |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workspace.variables.list();
```

#### Response

##### Type

Array of [WorkspaceVariablesListResponseItem](/src/types/workspace-variables-list-response-item.ts)

##### Example

```typescript
[{}]
```

### Update a workspace variable <a name="patch"></a>

Update an existing workspace variable. Secret values are encrypted and stored securely; the API will never return secret values.

**API Endpoint**: `PATCH /workspace/variables`

#### Parameters

| Parameter        | Required | Description | Example            |
| ---------------- | :------: | ----------- | ------------------ |
| `data`           |    ✗     |             | `{"id": "string"}` |
| `└─ apiId`       |    ✗     |             | `"string"`         |
| `└─ description` |    ✗     |             | `"string"`         |
| `└─ id`          |    ✓     |             | `"string"`         |
| `└─ isSecret`    |    ✗     |             | `true`             |
| `└─ name`        |    ✗     |             | `"string"`         |
| `└─ originId`    |    ✗     |             | `"string"`         |
| `└─ value`       |    ✗     |             | `"string"`         |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workspace.variables.patch();
```

#### Response

##### Type

[WorkspaceVariablesPatchResponse](/src/types/workspace-variables-patch-response.ts)

##### Example

```typescript
{}
```

### Create a workspace variable <a name="create"></a>

Create a new workspace variable. Secret values are encrypted and stored securely; the API will never return secret values.

**API Endpoint**: `POST /workspace/variables`

#### Parameters

| Parameter        | Required | Description | Example              |
| ---------------- | :------: | ----------- | -------------------- |
| `data`           |    ✗     |             | `{"name": "string"}` |
| `└─ apiId`       |    ✗     |             | `"string"`           |
| `└─ description` |    ✗     |             | `"string"`           |
| `└─ isSecret`    |    ✗     |             | `true`               |
| `└─ name`        |    ✓     |             | `"string"`           |
| `└─ originId`    |    ✗     |             | `"string"`           |
| `└─ value`       |    ✗     |             | `"string"`           |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workspace.variables.create();
```

#### Response

##### Type

[WorkspaceVariablesCreateResponse](/src/types/workspace-variables-create-response.ts)

##### Example

```typescript
{}
```
