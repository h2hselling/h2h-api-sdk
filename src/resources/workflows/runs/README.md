# workflows.runs

## Module Functions

### Delete a workflow run <a name="delete"></a>

Delete a workflow run and its associated task outputs by the run ID.

**API Endpoint**: `DELETE /workflows/runs/{id}`

#### Parameters

| Parameter | Required | Description         | Example    |
| --------- | :------: | ------------------- | ---------- |
| `id`      |    ✓     | The workflow run ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.runs.delete({ id: "string" });
```

#### Response

##### Type

[WorkflowsRunsDeleteResponse](/src/types/workflows-runs-delete-response.ts)

##### Example

```typescript
{"id": "string", "workflowId": "string"}
```

### List workflow runs <a name="list"></a>

Retrieve a paginated list of workflow runs. Optionally filter by workflow origin or specific workflow version.

**API Endpoint**: `GET /workflows/runs`

#### Parameters

| Parameter | Required | Description                                                                   | Example    |
| --------- | :------: | ----------------------------------------------------------------------------- | ---------- |
| `limit`   |    ✗     | Number of items per page                                                      | `123.0`    |
| `origin`  |    ✗     | Filter by workflow origin ID. Returns runs for all versions of this workflow. | `"string"` |
| `page`    |    ✗     | Page number (1-based)                                                         | `123.0`    |
| `version` |    ✗     | Filter by specific workflow version ID.                                       | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.runs.list();
```

#### Response

##### Type

Array of [WorkflowsRunsListResponseItem](/src/types/workflows-runs-list-response-item.ts)

##### Example

```typescript
[{"id": "string", "workflowId": "string"}]
```

### Get a workflow run <a name="get"></a>

Retrieve a single workflow run by its ID, including its current status.

**API Endpoint**: `GET /workflows/runs/{id}`

#### Parameters

| Parameter | Required | Description         | Example    |
| --------- | :------: | ------------------- | ---------- |
| `id`      |    ✓     | The workflow run ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.runs.get({ id: "string" });
```

#### Response

##### Type

[WorkflowsRunsGetResponse](/src/types/workflows-runs-get-response.ts)

##### Example

```typescript
{"id": "string", "workflowId": "string"}
```

### Create a workflow run <a name="create"></a>

Create a new workflow run in IDLE status. Use the dispatch endpoint to trigger execution.

**API Endpoint**: `POST /workflows/runs`

#### Parameters

| Parameter              | Required | Description                                                           | Example    |
| ---------------------- | :------: | --------------------------------------------------------------------- | ---------- |
| `workflowId`           |    ✓     | The workflow version ID to run                                        | `"string"` |
| `additionalProperties` |    ✗     |                                                                       | `{}`       |
| `executionType`        |    ✗     | The execution type (EVENT for event-triggered, INVOCATION for manual) | `"EVENT"`  |
| `input`                |    ✗     | The input data for the workflow run                                   | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.runs.create({ workflowId: "string" });
```

#### Response

##### Type

[WorkflowsRunsCreateResponse](/src/types/workflows-runs-create-response.ts)

##### Example

```typescript
{"id": "string", "workflowId": "string"}
```

## Submodules

- [dispatch](dispatch/README.md) - dispatch
