# workflows

## Module Functions

### Delete a workflow <a name="delete"></a>

Delete a workflow (workflow origin) and all its associated versions by the workflow origin ID.

**API Endpoint**: `DELETE /workflows/{id}`

#### Parameters

| Parameter | Required | Description            | Example    |
| --------- | :------: | ---------------------- | ---------- |
| `id`      |    ✓     | The workflow origin ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.delete({ id: "string" });
```

#### Response

##### Type

[WorkflowsDeleteResponse](/src/types/workflows-delete-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "updatedAt": "string", "userId": "string", "workflowId": "string"}
```

### List workflows <a name="list"></a>

Retrieve a paginated list of workflows (workflow origins) for the authenticated user. Each workflow origin represents a collection of workflow versions.

**API Endpoint**: `GET /workflows`

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
const res = await client.workflows.list();
```

#### Response

##### Type

Array of [WorkflowsListResponseItem](/src/types/workflows-list-response-item.ts)

##### Example

```typescript
[{"createdAt": "string", "description": "string", "id": "string", "name": "string", "updatedAt": "string", "userId": "string", "workflowId": "string"}]
```

### Get a workflow <a name="get"></a>

Retrieve a single workflow (workflow origin) by its ID.

**API Endpoint**: `GET /workflows/{id}`

#### Parameters

| Parameter | Required | Description            | Example    |
| --------- | :------: | ---------------------- | ---------- |
| `id`      |    ✓     | The workflow origin ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.get({ id: "string" });
```

#### Response

##### Type

[WorkflowsGetResponse](/src/types/workflows-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "updatedAt": "string", "userId": "string", "workflowId": "string"}
```

### Update a workflow <a name="patch"></a>

Update an existing workflow (workflow origin) by its ID. Only the provided fields will be updated.

**API Endpoint**: `PATCH /workflows/{id}`

#### Parameters

| Parameter              | Required | Description                         | Example    |
| ---------------------- | :------: | ----------------------------------- | ---------- |
| `id`                   |    ✓     | The workflow origin ID              | `"string"` |
| `additionalProperties` |    ✗     |                                     | `{}`       |
| `description`          |    ✗     | Updated description of the workflow | `"string"` |
| `name`                 |    ✗     | Updated name of the workflow        | `"string"` |
| `workflowId`           |    ✗     | Updated active workflow version ID  | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.patch({ id: "string" });
```

#### Response

##### Type

[WorkflowsPatchResponse](/src/types/workflows-patch-response.ts)

##### Example

```typescript
{"createdAt": "string", "description": "string", "id": "string", "name": "string", "updatedAt": "string", "userId": "string", "workflowId": "string"}
```

### Create a workflow <a name="create"></a>

Create a new workflow (workflow origin). This creates the top-level workflow container that holds versioned workflow definitions.

**API Endpoint**: `POST /workflows`

#### Parameters

| Parameter              | Required | Description                    | Example    |
| ---------------------- | :------: | ------------------------------ | ---------- |
| `description`          |    ✓     | Description of the workflow    | `"string"` |
| `name`                 |    ✓     | Name of the workflow           | `"string"` |
| `active`               |    ✗     | Whether the workflow is active | `true`     |
| `additionalProperties` |    ✗     |                                | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.create({
  description: "string",
  name: "string",
});
```

#### Response

##### Type

[WorkflowsCreateResponse](/src/types/workflows-create-response.ts)

##### Example

```typescript
{}
```

## Submodules

- [dispatch](dispatch/README.md) - dispatch
- [invoke](invoke/README.md) - invoke
- [runs](runs/README.md) - runs
- [versions](versions/README.md) - versions
