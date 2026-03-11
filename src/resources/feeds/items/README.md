# feeds.items

## Module Functions

### Get a specific feed item by ID <a name="get"></a>

**API Endpoint**: `GET /feeds/items/{id}`

#### Parameters

| Parameter | Required | Description                         | Example    |
| --------- | :------: | ----------------------------------- | ---------- |
| `id`      |    ✓     | The ID of the feed item to retrieve | `"string"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.items.get({ id: "string" });
```

#### Response

##### Type

[FeedsItemsGetResponse](/src/types/feeds-items-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "data": {}, "feedId": "string", "id": "string", "metadata": {}}
```

### Create a new feed item for an API feed <a name="create"></a>

**API Endpoint**: `POST /feeds/items`

#### Parameters

| Parameter     | Required | Description | Example                                            |
| ------------- | :------: | ----------- | -------------------------------------------------- |
| `data`        |    ✗     |             | `{"data": {}, "feedId": "string", "metadata": {}}` |
| `└─ data`     |    ✓     |             | `{}`                                               |
| `└─ feedId`   |    ✓     |             | `"string"`                                         |
| `└─ metadata` |    ✓     |             | `{}`                                               |
| `└─ options`  |    ✗     |             | `{}`                                               |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.items.create();
```

#### Response

##### Type

[FeedsItemsCreateResponse](/src/types/feeds-items-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "feedId": "string", "id": "string", "metadata": {}, "workflowRuns": [{"id": "string", "workflowId": "string"}]}
```
