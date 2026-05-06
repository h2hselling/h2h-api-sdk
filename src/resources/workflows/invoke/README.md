# workflows.invoke

## Module Functions

### Invoke a workflow <a name="create"></a>

Invoke a workflow run. This is a synchronous call that waits for the workflow run to complete and returns the result.

**API Endpoint**: `POST /workflows/{workflow_id}/invoke`

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
const res = await client.workflows.invoke.create({ workflowId: "string" });
```

#### Response

##### Type

[WorkflowsInvokeCreateResponse](/src/types/workflows-invoke-create-response.ts)

##### Example

```typescript
{"id": "string", "status": "string", "workflow": {"id": "string", "name": "string"}}
```
