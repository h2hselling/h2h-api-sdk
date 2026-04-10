# workflows.versions.tasks

## Module Functions

### Delete a workflow task <a name="delete"></a>

Delete a specific workflow task by its ID.

**API Endpoint**: `DELETE /workflows/versions/{version_id}/tasks/{task_id}`

#### Parameters

| Parameter   | Required | Description             | Example    |
| ----------- | :------: | ----------------------- | ---------- |
| `taskId`    |    ✓     | The workflow task ID    | `"string"` |
| `versionId` |    ✓     | The workflow version ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.tasks.delete({
  taskId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsTasksDeleteResponse](/src/types/workflows-versions-tasks-delete-response.ts)

##### Example

```typescript
{"id": "string", "name": "string", "parentTasks": {}, "toolId": "string", "workflowId": "string"}
```

### Get a workflow task <a name="get"></a>

Retrieve a single workflow task by its ID.

**API Endpoint**: `GET /workflows/versions/{version_id}/tasks/{task_id}`

#### Parameters

| Parameter   | Required | Description             | Example    |
| ----------- | :------: | ----------------------- | ---------- |
| `taskId`    |    ✓     | The workflow task ID    | `"string"` |
| `versionId` |    ✓     | The workflow version ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.tasks.get({
  taskId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsTasksGetResponse](/src/types/workflows-versions-tasks-get-response.ts)

##### Example

```typescript
{}
```

### Update a workflow task <a name="patch"></a>

Update an existing workflow task. Only the provided fields will be updated.

**API Endpoint**: `PATCH /workflows/versions/{version_id}/tasks/{task_id}`

#### Parameters

| Parameter              | Required | Description                                                                               | Example    |
| ---------------------- | :------: | ----------------------------------------------------------------------------------------- | ---------- |
| `id`                   |    ✓     | UUID v4 of the task to update                                                             | `"string"` |
| `taskId`               |    ✓     | The workflow task ID                                                                      | `"string"` |
| `type`                 |    ✓     | Type of the task update                                                                   | `"delete"` |
| `versionId`            |    ✓     | The workflow version ID                                                                   | `"string"` |
| `additionalProperties` |    ✗     |                                                                                           | `{}`       |
| `config`               |    ✗     | Arbitrary JSON config object                                                              | `{}`       |
| `description`          |    ✗     | Description of the task                                                                   | `"string"` |
| `name`                 |    ✗     | Name of the task                                                                          | `"string"` |
| `outputSchema`         |    ✗     | Output schema as JSON                                                                     | `{}`       |
| `parentTasks`          |    ✗     | Parent tasks as a JSON object. {<task_id>: {dependent: true, conditions:<condition_set>}} | `{}`       |
| `toolName`             |    ✗     | Name of the tool to create the task for. e.g "Code Execution"                             | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.tasks.patch({
  id: "string",
  type: "delete",
  taskId: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsTasksPatchResponse](/src/types/workflows-versions-tasks-patch-response.ts)

##### Example

```typescript
{"id": "string", "name": "string", "parentTasks": {}, "toolId": "string", "workflowId": "string"}
```

### Create a workflow task <a name="create"></a>

Create a new task under a specific workflow version.

**API Endpoint**: `POST /workflows/versions/{version_id}/tasks`

#### Parameters

| Parameter              | Required | Description                                                                               | Example    |
| ---------------------- | :------: | ----------------------------------------------------------------------------------------- | ---------- |
| `config`               |    ✓     | Arbitrary JSON config object                                                              | `{}`       |
| `description`          |    ✓     | Description of the task                                                                   | `"string"` |
| `name`                 |    ✓     | Name of the task                                                                          | `"string"` |
| `outputSchema`         |    ✓     | Output schema as JSON                                                                     | `{}`       |
| `parentTasks`          |    ✓     | Parent tasks as a JSON object. {<task_id>: {dependent: true, conditions:<condition_set>}} | `{}`       |
| `toolName`             |    ✓     | Name of the tool to create the task for. e.g "Code Execution"                             | `"string"` |
| `versionId`            |    ✓     | The workflow version ID                                                                   | `"string"` |
| `additionalProperties` |    ✗     |                                                                                           | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.versions.tasks.create({
  config: {},
  description: "string",
  name: "string",
  outputSchema: {},
  parentTasks: {},
  toolName: "string",
  versionId: "string",
});
```

#### Response

##### Type

[WorkflowsVersionsTasksCreateResponse](/src/types/workflows-versions-tasks-create-response.ts)

##### Example

```typescript
{"id": "string", "name": "string", "parentTasks": {}, "toolId": "string", "workflowId": "string"}
```
