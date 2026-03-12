# workflows.versions

## Module Functions

### Delete a workflow version <a name="delete"></a>

Delete a specific workflow version by its ID.

**API Endpoint**: `DELETE /workflows/{origin_id}/versions/{version_id}`

#### Parameters

| Parameter   | Required | Description             | Example    |
| ----------- | :------: | ----------------------- | ---------- |
| `originId`  |    ✓     | The workflow origin ID  | `"string"` |
| `versionId` |    ✓     | The workflow version ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.delete({
  originId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsDeleteResponse](/src/types/workflows-versions-delete-response.ts)

##### Example

```typescript
{"access": "string", "active": true, "createdAt": "string", "description": "string", "feedId": "string", "id": "string", "name": "string", "userId": "string"}
```

### List workflow versions <a name="list"></a>

Retrieve a paginated list of workflow versions belonging to a specific workflow origin.

**API Endpoint**: `GET /workflows/{origin_id}/versions`

#### Parameters

| Parameter  | Required | Description              | Example    |
| ---------- | :------: | ------------------------ | ---------- |
| `originId` |    ✓     | The workflow origin ID   | `"string"` |
| `limit`    |    ✗     | Number of items per page | `123.0`    |
| `page`     |    ✗     | Page number (1-based)    | `123.0`    |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.list({ originId: "string" });
```

#### Response

##### Type

Array of [WorkflowsVersionsListResponseItem](/src/types/workflows-versions-list-response-item.ts)

##### Example

```typescript
[{"access": "string", "active": true, "createdAt": "string", "description": "string", "feedId": "string", "id": "string", "name": "string", "userId": "string"}]
```

### Get a workflow version <a name="get"></a>

Retrieve a single workflow version by its ID.

**API Endpoint**: `GET /workflows/{origin_id}/versions/{version_id}`

#### Parameters

| Parameter   | Required | Description             | Example    |
| ----------- | :------: | ----------------------- | ---------- |
| `originId`  |    ✓     | The workflow origin ID  | `"string"` |
| `versionId` |    ✓     | The workflow version ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.get({
  originId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsGetResponse](/src/types/workflows-versions-get-response.ts)

##### Example

```typescript
{"access": "string", "active": true, "createdAt": "string", "description": "string", "feedId": "string", "id": "string", "name": "string", "userId": "string"}
```

### Update a workflow version <a name="patch"></a>

Update an existing workflow version. Only the provided fields will be updated.

**API Endpoint**: `PATCH /workflows/{origin_id}/versions/{version_id}`

#### Parameters

| Parameter              | Required | Description             | Example    |
| ---------------------- | :------: | ----------------------- | ---------- |
| `originId`             |    ✓     | The workflow origin ID  | `"string"` |
| `versionId`            |    ✓     | The workflow version ID | `"string"` |
| `access`               |    ✗     | Updated access level    | `"string"` |
| `active`               |    ✗     | Updated active status   | `true`     |
| `additionalProperties` |    ✗     |                         | `{}`       |
| `description`          |    ✗     | Updated description     | `"string"` |
| `instructions`         |    ✗     | Updated instructions    | `"string"` |
| `name`                 |    ✗     | Updated name            | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.patch({
  originId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsPatchResponse](/src/types/workflows-versions-patch-response.ts)

##### Example

```typescript
{"access": "string", "active": true, "createdAt": "string", "description": "string", "feedId": "string", "id": "string", "name": "string", "userId": "string"}
```

### Create a workflow version <a name="create"></a>

Create a new workflow version under a specific workflow origin.

**API Endpoint**: `POST /workflows/{origin_id}/versions`

#### Parameters

| Parameter              | Required | Description                            | Example    |
| ---------------------- | :------: | -------------------------------------- | ---------- |
| `description`          |    ✓     | Description of the workflow version    | `"string"` |
| `name`                 |    ✓     | Name of the workflow version           | `"string"` |
| `originId`             |    ✓     | The workflow origin ID                 | `"string"` |
| `access`               |    ✗     | Access level (e.g. PRIVATE, PUBLIC)    | `"string"` |
| `active`               |    ✗     | Whether this version is active         | `true`     |
| `additionalProperties` |    ✗     |                                        | `{}`       |
| `instructions`         |    ✗     | Optional instructions for the workflow | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.create({
  description: "string",
  name: "string",
  originId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsCreateResponse](/src/types/workflows-versions-create-response.ts)

##### Example

```typescript
{"access": "string", "active": true, "createdAt": "string", "description": "string", "feedId": "string", "id": "string", "name": "string", "userId": "string"}
```
