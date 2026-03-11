# workflow.run.trigger

## Module Functions

### Trigger a new workflow run <a name="create"></a>

**API Endpoint**: `POST /workflow/run/trigger`

#### Parameters

| Parameter          | Required | Description                           | Example                       |
| ------------------ | :------: | ------------------------------------- | ----------------------------- |
| `data`             |    ✗     |                                       | `{"workflowRunId": "string"}` |
| `└─ workflowRunId` |    ✓     | The ID of the workflow run to trigger | `"string"`                    |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflow.run.trigger.create();
```

#### Response

##### Type

[WorkflowRunTriggerCreateResponse](/src/types/workflow-run-trigger-create-response.ts)

##### Example

```typescript
{"id": "string", "workflowId": "string"}
```
