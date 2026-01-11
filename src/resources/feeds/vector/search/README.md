# feeds.vector.search

## Module Functions

### Run a query against feed embeddings <a name="create"></a>

**API Endpoint**: `POST /feeds/{id}/vector/search`

#### Parameters

| Parameter           | Required | Description                                      | Example                                                                                     |
| ------------------- | :------: | ------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| `id`                |    ✓     | The ID of the feed to search against             | `"123e4567-e89b-12d3-a456-426614174000"`                                                    |
| `data`              |    ✗     |                                                  | `{"endDate": "1970-01-01T00:00:00", "query": "string", "startDate": "1970-01-01T00:00:00"}` |
| `└─ endDate`        |    ✓     | End date for filtering feed items                | `"1970-01-01T00:00:00"`                                                                     |
| `└─ includeOutputs` |    ✗     | Whether to include outputs in the search results | `true`                                                                                      |
| `└─ limit`          |    ✗     | Maximum number of results to return              | `123`                                                                                       |
| `└─ query`          |    ✓     |                                                  | `"string"`                                                                                  |
| `└─ startDate`      |    ✓     | Start date for filtering feed items              | `"1970-01-01T00:00:00"`                                                                     |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.feeds.vector.search.create({
  id: "123e4567-e89b-12d3-a456-426614174000",
});
```

#### Response

##### Type

Array of [FeedsVectorSearchCreateResponseItem](/src/types/feeds-vector-search-create-response-item.ts)

##### Example

```typescript
[{"chunkIndex": 123, "createdAt": "1970-01-01T00:00:00", "id": "string", "resourceId": "string", "resourceType": "feed_handler_output", "similarity": 123.0}]
```
