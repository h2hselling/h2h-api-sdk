# tools.internet-search

## Module Functions

### Internet search tool <a name="create"></a>

**API Endpoint**: `POST /tools/internet_search`

#### Parameters

| Parameter  | Required | Description                                      | Example    |
| ---------- | :------: | ------------------------------------------------ | ---------- |
| `messages` |    ✓     |                                                  | `[{}]`     |
| `system`   |    ✓     |                                                  | `"string"` |
| `maxUses`  |    ✗     | The maximum number of times the tool can be used | `123`      |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.internetSearch.create({
  messages: [{}],
  system: "string",
});
```

#### Response

##### Type

Array of [ToolsInternetSearchCreateResponseItem](/src/types/tools-internet-search-create-response-item.ts)

##### Example

```typescript
[{"text": "string", "type": "string"}]
```
