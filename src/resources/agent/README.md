# agent

## Module Functions

### Get agent chat data <a name="list"></a>

Retrieve the chat record and persisted display messages for a given chat session.

**API Endpoint**: `GET /agent`

#### Parameters

| Parameter | Required | Description                      | Example    |
| --------- | :------: | -------------------------------- | ---------- |
| `chatId`  |    ✓     | The chat session ID to retrieve. | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.list({ chatId: "string" });
```

#### Response

##### Type

[AgentListResponse](/src/types/agent-list-response.ts)

##### Example

```typescript
{"chat": {}, "messages": [{"content": "could be anything", "role": "assistant"}]}
```

### Run an agent <a name="create"></a>

Send a message to a named MCP agent and receive its response. The agent may call API tools and delegate to sub-agents to fulfil the request.

**API Endpoint**: `POST /agent`

#### Parameters

| Parameter              | Required | Description                                                                                                       | Example    |
| ---------------------- | :------: | ----------------------------------------------------------------------------------------------------------------- | ---------- |
| `agent`                |    ✓     | The name of the agent to run (e.g. "orchestrator", "querier", "invoker").                                         | `"string"` |
| `message`              |    ✓     | The user message / task for the agent to complete.                                                                | `"string"` |
| `additionalProperties` |    ✗     |                                                                                                                   | `{}`       |
| `chatId`               |    ✗     | The ID of the chat session. When provided, messages are persisted to storage so they can be polled by the client. | `"string"` |
| `context`              |    ✗     | Additional context to pass to the agent (e.g. current URL, page state).                                           | `{}`       |
| `maxIterations`        |    ✗     | Maximum number of tool-call iterations before the agent is forced to respond. Defaults to 15.                     | `123.0`    |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.create({ agent: "string", message: "string" });
```

#### Response

##### Type

[AgentCreateResponse](/src/types/agent-create-response.ts)

##### Example

```typescript
{"agent": "string", "messages": [{"content": "could be anything", "role": "assistant"}], "text": "string"}
```

## Submodules

- [build](build/README.md) - build
- [history](history/README.md) - history
