# agent.history

## Module Functions

### List agent chat history <a name="list"></a>

Retrieve a paginated list of chat sessions for the authenticated user, ordered by most recent first.

**API Endpoint**: `GET /agent/history`

#### Parameters

| Parameter | Required | Description                        | Example |
| --------- | :------: | ---------------------------------- | ------- |
| `limit`   |    ✗     | Maximum number of chats to return. | `123.0` |
| `offset`  |    ✗     | Offset for pagination.             | `123.0` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.agent.history.list();
```

#### Response

##### Type

[AgentHistoryListResponse](/src/types/agent-history-list-response.ts)

##### Example

```typescript
{"chats": [{}]}
```
