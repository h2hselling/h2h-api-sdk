# feeds

## Module Functions

### List all feeds <a name="list"></a>

**API Endpoint**: `GET /feeds`

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.list();
```

#### Response

##### Type

Array of [FeedsListResponseItem](/src/types/feeds-list-response-item.ts)

##### Example

```typescript
[{"config": {}, "description": "string", "feedType": "API", "id": "string", "name": "string"}]
```

### Get a specific feed by ID <a name="get"></a>

**API Endpoint**: `GET /feeds/{id}`

#### Parameters

| Parameter | Required | Description                    | Example                                  |
| --------- | :------: | ------------------------------ | ---------------------------------------- |
| `id`      |    ✓     | The ID of the feed to retrieve | `"123e4567-e89b-12d3-a456-426614174000"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.get({
  id: "123e4567-e89b-12d3-a456-426614174000",
});
```

#### Response

##### Type

[FeedsGetResponse](/src/types/feeds-get-response.ts)

##### Example

```typescript
{"config": {}, "description": "string", "feedType": "API", "id": "string", "name": "string"}
```

### Create a new feed <a name="create"></a>

**API Endpoint**: `POST /feeds`

#### Parameters

| Parameter        | Required | Description | Example                                                          |
| ---------------- | :------: | ----------- | ---------------------------------------------------------------- |
| `data`           |    ✗     |             | `{"description": "string", "feedType": "API", "name": "string"}` |
| `└─ accountId`   |    ✗     |             | `"string"`                                                       |
| `└─ config`      |    ✗     |             | `{"handle": "string", "trustedSenders": ["string"]}`             |
| `└─ description` |    ✓     |             | `"string"`                                                       |
| `└─ feedType`    |    ✓     |             | `"API"`                                                          |
| `└─ name`        |    ✓     |             | `"string"`                                                       |
| `└─ userId`      |    ✗     |             | `"string"`                                                       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.create();
```

#### Response

##### Type

[FeedsCreateResponse](/src/types/feeds-create-response.ts)

##### Example

```typescript
{"config": {}, "description": "string", "feedType": "API", "id": "string", "name": "string"}
```

## Submodules

- [items](items/README.md) - items
- [vector](vector/README.md) - vector
