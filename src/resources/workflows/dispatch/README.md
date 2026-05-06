# workflows.dispatch

## Module Functions

### Dispatch a workflow <a name="create"></a>

Dispatch a new workflow run asynchronously. This call returns the workflow run ID so the caller can poll for the result.

**API Endpoint**: `POST /workflows/{workflow_id}/dispatch`

#### Parameters

| Parameter    | Required | Description                                                                                       | Example         |
| ------------ | :------: | ------------------------------------------------------------------------------------------------- | --------------- |
| `workflowId` |    ✓     |                                                                                                   | `"string"`      |
| `data`       |    ✗     |                                                                                                   | `{"input": {}}` |
| `└─ input`   |    ✓     | The input for the workflow run                                                                    | `{}`            |
| `└─ inputs`  |    ✗     | The inputs for the workflow run (deprecated, use input instead)                                   | `{}`            |
| `└─ runId`   |    ✗     | Optional: The ID of the workflow run to invoke. Used for re-invoking a workflow run.              | `"string"`      |
| `└─ taskId`  |    ✗     | Optional: The ID of the task to invoke. Used for re-invoking a workflow run from a specific task. | `"string"`      |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.dispatch.create({ workflowId: "string" });
```

#### Response

##### Type

[WorkflowsDispatchCreateResponse](/src/types/workflows-dispatch-create-response.ts)

##### Example

```typescript
{"id": "string"}
```
