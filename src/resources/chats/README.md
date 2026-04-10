# chats

## Module Functions

### Get a chat <a name="get"></a>

Retrieve a chat by its ID, including its stored message history.

**API Endpoint**: `GET /chats/{id}`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.chats.get({ id: "string" });
```

#### Response

##### Type

[ChatsGetResponse](/src/types/chats-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "messages": [{"content": "string", "role": "assistant"}], "name": "string", "status": "ERROR", "type": "AGENT/BUILD/WORKFLOW", "userId": "string"}
```
