# workflows.dispatch

## Module Functions

### Dispatch a new workflow run. This is an asynchronous call that will return the workflow run ID and allow you to poll for the result. <a name="create"></a>

**API Endpoint**: `POST /workflows/{workflow_id}/dispatch`

#### Parameters

| Parameter    | Required | Description | Example         |
| ------------ | :------: | ----------- | --------------- |
| `workflowId` |    ✓     |             | `"string"`      |
| `data`       |    ✗     |             | `{"input": {}}` |
| `└─ input`   |    ✓     |             | `{}`            |

#### Example Snippet

```typescript
import Client from "api_ts";

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
