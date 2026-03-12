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

### Continue a chat <a name="patch"></a>

Continue an existing chat by appending a new user query and returning the updated messages.

**API Endpoint**: `PATCH /chats/{id}`

#### Parameters

| Parameter               | Required | Description | Example               |
| ----------------------- | :------: | ----------- | --------------------- |
| `id`                    |    ✓     |             | `"string"`            |
| `data`                  |    ✗     |             | `{"query": "string"}` |
| `└─ isWebSearchEnabled` |    ✗     |             | `true`                |
| `└─ query`              |    ✓     |             | `"string"`            |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.chats.patch({ id: "string" });
```

#### Response

##### Type

[ChatsPatchResponse](/src/types/chats-patch-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "messages": [{"content": "string", "role": "assistant"}], "name": "string", "status": "ERROR", "type": "AGENT/BUILD/WORKFLOW", "userId": "string"}
```

### Create a chat <a name="create"></a>

Create a new chat for the provided ID and initialize it with the first query.

**API Endpoint**: `POST /chats/{id}`

#### Parameters

| Parameter               | Required | Description | Example                                                                               |
| ----------------------- | :------: | ----------- | ------------------------------------------------------------------------------------- |
| `id`                    |    ✓     |             | `"string"`                                                                            |
| `query`                 |    ✓     |             | `"string"`                                                                            |
| `data`                  |    ✗     |             | `{"endDate": "string", "feedId": "string", "query": "string", "startDate": "string"}` |
| `└─ endDate`            |    ✓     |             | `"string"`                                                                            |
| `└─ feedId`             |    ✓     |             | `"string"`                                                                            |
| `└─ isWebSearchEnabled` |    ✗     |             | `true`                                                                                |
| `└─ query`              |    ✓     |             | `"string"`                                                                            |
| `└─ startDate`          |    ✓     |             | `"string"`                                                                            |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.chats.create({ id: "string", query: "string" });
```

#### Response

##### Type

[ChatsCreateResponse](/src/types/chats-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "messages": [{"content": "string", "role": "assistant"}], "name": "string", "status": "ERROR", "type": "AGENT/BUILD/WORKFLOW", "userId": "string"}
```
