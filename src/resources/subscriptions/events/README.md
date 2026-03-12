# subscriptions.events

## Module Functions

### Delete an event subscription <a name="delete"></a>

Delete an event subscription by its ID.

**API Endpoint**: `DELETE /subscriptions/events/{id}`

#### Parameters

| Parameter | Required | Description               | Example    |
| --------- | :------: | ------------------------- | ---------- |
| `id`      |    ✓     | The event subscription ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.subscriptions.events.delete({ id: "string" });
```

#### Response

##### Type

[SubscriptionsEventsDeleteResponse](/src/types/subscriptions-events-delete-response.ts)

##### Example

```typescript
{"consumerId": "string", "consumerType": "workflow_origins", "createdAt": "string", "events": ["string"], "id": "string", "producerId": "string", "producerType": "feeds"}
```

### List event subscriptions <a name="list"></a>

Retrieve a paginated list of event subscriptions for the authenticated user.

**API Endpoint**: `GET /subscriptions/events`

#### Parameters

| Parameter | Required | Description              | Example |
| --------- | :------: | ------------------------ | ------- |
| `limit`   |    ✗     | Number of items per page | `123.0` |
| `page`    |    ✗     | Page number (1-based)    | `123.0` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.subscriptions.events.list();
```

#### Response

##### Type

Array of [SubscriptionsEventsListResponseItem](/src/types/subscriptions-events-list-response-item.ts)

##### Example

```typescript
[{"consumerId": "string", "consumerType": "workflow_origins", "createdAt": "string", "events": ["string"], "id": "string", "producerId": "string", "producerType": "feeds"}]
```

### Get an event subscription <a name="get"></a>

Retrieve a single event subscription by its ID.

**API Endpoint**: `GET /subscriptions/events/{id}`

#### Parameters

| Parameter | Required | Description               | Example    |
| --------- | :------: | ------------------------- | ---------- |
| `id`      |    ✓     | The event subscription ID | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.subscriptions.events.get({ id: "string" });
```

#### Response

##### Type

[SubscriptionsEventsGetResponse](/src/types/subscriptions-events-get-response.ts)

##### Example

```typescript
{"consumerId": "string", "consumerType": "workflow_origins", "createdAt": "string", "events": ["string"], "id": "string", "producerId": "string", "producerType": "feeds"}
```

### Create an event subscription <a name="create"></a>

Create a new event subscription that links a producer to a consumer via event patterns.

**API Endpoint**: `POST /subscriptions/events`

#### Parameters

| Parameter              | Required | Description                                                             | Example              |
| ---------------------- | :------: | ----------------------------------------------------------------------- | -------------------- |
| `consumerId`           |    ✓     | The ID of the consumer resource                                         | `"string"`           |
| `consumerType`         |    ✓     | The type of the consumer resource                                       | `"workflow_origins"` |
| `events`               |    ✓     | Array of event patterns to subscribe to (e.g. ["feed_items", "create"]) | `["string"]`         |
| `producerId`           |    ✓     | The ID of the producer resource                                         | `"string"`           |
| `producerType`         |    ✓     | The type of the producer resource                                       | `"feeds"`            |
| `additionalProperties` |    ✗     |                                                                         | `{}`                 |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.subscriptions.events.create({
  consumerId: "string",
  consumerType: "workflow_origins",
  events: ["string"],
  producerId: "string",
  producerType: "feeds",
});
```

#### Response

##### Type

[SubscriptionsEventsCreateResponse](/src/types/subscriptions-events-create-response.ts)

##### Example

```typescript
{"consumerId": "string", "consumerType": "workflow_origins", "createdAt": "string", "events": ["string"], "id": "string", "producerId": "string", "producerType": "feeds"}
```
