# search-groups.items

## Module Functions

### Get a search item by id <a name="get"></a>

**API Endpoint**: `GET /search_groups/items/{id}`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.searchGroups.items.get({ id: "string" });
```

#### Response

##### Type

[SearchGroupsItemsGetResponse](/src/types/search-groups-items-get-response.ts)

##### Example

```typescript
{"createdAt": "string", "id": "string", "searchGroupId": "string", "value": {"aliases": ["string"], "key": "string"}}
```

### List search items in a search group <a name="list"></a>

**API Endpoint**: `GET /search_groups/{id}/items`

#### Parameters

| Parameter | Required | Description | Example    |
| --------- | :------: | ----------- | ---------- |
| `id`      |    ✓     |             | `"string"` |
| `limit`   |    ✗     |             | `123.0`    |
| `page`    |    ✗     |             | `123.0`    |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.searchGroups.items.list({ id: "string" });
```

#### Response

##### Type

Array of [SearchGroupsItemsListResponseItem](/src/types/search-groups-items-list-response-item.ts)

##### Example

```typescript
[{"createdAt": "string", "id": "string", "searchGroupId": "string", "value": {"aliases": ["string"], "key": "string"}}]
```

### Create a new search item in a search group <a name="create"></a>

**API Endpoint**: `POST /search_groups/{id}/items`

#### Parameters

| Parameter | Required | Description | Example                                    |
| --------- | :------: | ----------- | ------------------------------------------ |
| `id`      |    ✓     |             | `"string"`                                 |
| `data`    |    ✗     |             | `{"aliases": ["string"], "key": "string"}` |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.searchGroups.items.create({ id: "string" });
```

#### Response

##### Type

Union of[SearchGroupsItemsCreateResponseUnion0Obj0](/src/types/search-groups-items-create-response-union0-obj0.ts), [SearchGroupsItemsCreateResponseUnion0Obj1](/src/types/search-groups-items-create-response-union0-obj1.ts)

##### Example

```typescript
{"aliases": ["string"], "key": "string"}
```
