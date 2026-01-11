# agent.build.workflow

## Module Functions

### Get the output of a workflow <a name="list"></a>

**API Endpoint**: `GET /agent/build/workflow`

#### Parameters

| Parameter | Required | Description                     | Example    |
| --------- | :------: | ------------------------------- | ---------- |
| `chat`    |    ✗     | The ID of the chat to continue. | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.build.workflow.list();
```

#### Response

##### Type

[AgentBuildWorkflowListResponse](/src/types/agent-build-workflow-list-response.ts)

##### Example

```typescript
{"chat": {"createdAt": "string", "id": "string", "messages": [{"content": "string", "role": "assistant"}], "name": "string", "status": "ERROR", "type": "AGENT/BUILD/WORKFLOW", "userId": "string"}, "messages": [{}], "output": {}}
```

### Build a workflow <a name="create"></a>

**API Endpoint**: `POST /agent/build/workflow`

#### Parameters

| Parameter    | Required | Description                                 | Example                 |
| ------------ | :------: | ------------------------------------------- | ----------------------- |
| `feed`       |    ✓     | The ID of the feed to build a workflow for. | `"string"`              |
| `chat`       |    ✗     | The ID of the chat to continue.             | `"string"`              |
| `data`       |    ✗     |                                             | `{"message": "string"}` |
| `└─ message` |    ✓     |                                             | `"string"`              |
| `└─ stream`  |    ✗     |                                             | `true`                  |
| `workflow`   |    ✗     | The ID of the workflow to build out.        | `"string"`              |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.build.workflow.create({ feed: "string" });
```

#### Response

##### Type

[AgentBuildWorkflowCreateResponse](/src/types/agent-build-workflow-create-response.ts)

##### Example

```typescript
{}
```
