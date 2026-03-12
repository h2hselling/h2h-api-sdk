# workflows.runs.dispatch

## Module Functions

### Dispatch a workflow run <a name="create"></a>

Dispatch an existing workflow run for asynchronous execution. The run must be in IDLE status. This publishes the run to the workflow handler for processing.

**API Endpoint**: `POST /workflows/runs/{id}/dispatch`

#### Parameters

| Parameter | Required | Description                     | Example    |
| --------- | :------: | ------------------------------- | ---------- |
| `id`      |    ✓     | The workflow run ID to dispatch | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.workflows.runs.dispatch.create({ id: "string" });
```

#### Response

##### Type

[WorkflowsRunsDispatchCreateResponse](/src/types/workflows-runs-dispatch-create-response.ts)

##### Example

```typescript
{"id": "string", "status": "string"}
```
