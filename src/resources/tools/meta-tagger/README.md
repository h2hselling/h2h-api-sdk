# tools.meta-tagger

## Module Functions

### Meta Tag a feed item <a name="create"></a>

**API Endpoint**: `POST /tools/meta_tagger`

#### Parameters

| Parameter         | Required | Description                                                         | Example                                          |
| ----------------- | :------: | ------------------------------------------------------------------- | ------------------------------------------------ |
| `data`            |    ✗     |                                                                     | `{"data": "string", "searchGroups": ["string"]}` |
| `└─ data`         |    ✓     | The data to apply meta tags against                                 | `"string"`                                       |
| `└─ searchGroups` |    ✓     | The ids (uuids) of the meta tag search groups to apply meta tags to | `["string"]`                                     |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.metaTagger.create();
```

#### Response

##### Type

Array of [ToolsMetaTaggerCreateResponseItem](/src/types/tools-meta-tagger-create-response-item.ts)

##### Example

```typescript
[{"id": "string", "name": "string"}]
```
