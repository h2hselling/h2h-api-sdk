# tools.dictionary-search

## Module Functions

### Search for dictionary definitions related to a feed item <a name="create"></a>

**API Endpoint**: `POST /tools/dictionary_search`

#### Parameters

| Parameter      | Required | Description | Example      |
| -------------- | :------: | ----------- | ------------ |
| `data`         |    ✓     |             | `"string"`   |
| `searchGroups` |    ✓     |             | `["string"]` |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.dictionarySearch.create({
  data: "string",
  searchGroups: ["string"],
});
```

#### Response

##### Type

Array of [ToolsDictionarySearchCreateResponseItem](/src/types/tools-dictionary-search-create-response-item.ts)

##### Example

```typescript
[{"id": "string", "value": "string"}]
```
