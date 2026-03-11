# workflows.invoke

## Module Functions

### Invoke a new workflow run. This is a synchronous call that will wait for the workflow run to complete and return the result. <a name="create"></a>

**API Endpoint**: `POST /workflows/{workflow_id}/invoke`

#### Parameters

| Parameter    | Required | Description | Example         |
| ------------ | :------: | ----------- | --------------- |
| `workflowId` |    ✓     |             | `"string"`      |
| `data`       |    ✗     |             | `{"input": {}}` |
| `└─ input`   |    ✓     |             | `{}`            |

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
