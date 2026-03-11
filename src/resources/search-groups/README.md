# search-groups

## Module Functions

### List search groups <a name="list"></a>

**API Endpoint**: `GET /search_groups`

#### Parameters

| Parameter | Required | Description | Example        |
| --------- | :------: | ----------- | -------------- |
| `limit`   |    ✗     |             | `123.0`        |
| `page`    |    ✗     |             | `123.0`        |
| `type`    |    ✗     |             | `"DICTIONARY"` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.searchGroups.list();
```

#### Response

##### Type

Array of [SearchGroupsListResponseItem](/src/types/search-groups-list-response-item.ts)

##### Example

```typescript
[{"createdAt": "string", "id": "string", "name": "string", "type": "string", "userId": "string"}]
```

### Get a search group by id <a name="get"></a>

**API Endpoint**: `GET /search_groups/{id}`

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
const res = await client.searchGroups.get({ id: "string" });
```

#### Response

##### Type

[SearchGroupsGetResponse](/src/types/search-groups-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "name": "string", "type": "string", "userId": "string"}
```

### Create a new dictionary <a name="create"></a>

**API Endpoint**: `POST /search_groups`

#### Parameters

| Parameter        | Required | Description | Example                                                         |
| ---------------- | :------: | ----------- | --------------------------------------------------------------- |
| `data`           |    ✗     |             | `{"description": "string", "name": "string", "type": "string"}` |
| `└─ description` |    ✓     |             | `"string"`                                                      |
| `└─ name`        |    ✓     |             | `"string"`                                                      |
| `└─ type`        |    ✓     |             | `"string"`                                                      |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.searchGroups.create();
```

#### Response

##### Type

[SearchGroupsCreateResponse](/src/types/search-groups-create-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "name": "string", "type": "string", "userId": "string"}
```

## Submodules

- [items](items/README.md) - items
