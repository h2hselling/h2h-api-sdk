# agent.abort

## Module Functions

### Abort an in-progress agent chat <a name="create"></a>

Mark a chat as ABORTED so any in-flight agent run for it exits at its next iteration boundary.

**API Endpoint**: `POST /agent/abort`

#### Parameters

| Parameter              | Required | Description                   | Example    |
| ---------------------- | :------: | ----------------------------- | ---------- |
| `chatId`               |    ✓     | The chat session ID to abort. | `"string"` |
| `additionalProperties` |    ✗     |                               | `{}`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.abort.create({ chatId: "string" });
```

#### Response

##### Type

[AgentAbortCreateResponse](/src/types/agent-abort-create-response.ts)

##### Example

```typescript
{"chatId": "string", "success": true}
```
