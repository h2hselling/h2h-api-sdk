# workflows.dispatch

## Module Functions

### Dispatch a workflow <a name="create"></a>

Dispatch a new workflow run asynchronously. This call returns the workflow run ID so the caller can poll for the result.

**API Endpoint**: `POST /workflows/{workflow_id}/dispatch`

#### Parameters

| Parameter    | Required | Description | Example          |
| ------------ | :------: | ----------- | ---------------- |
| `workflowId` |    ✓     |             | `"string"`       |
| `data`       |    ✗     |             | `{"inputs": {}}` |
| `└─ inputs`  |    ✓     |             | `{}`             |

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
