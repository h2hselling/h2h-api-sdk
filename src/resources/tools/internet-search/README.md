# tools.internet-search

## Module Functions

### Run internet search <a name="create"></a>

Use the internet search tool to answer a prompt with live web search support.

**API Endpoint**: `POST /tools/internet_search`

#### Parameters

| Parameter  | Required | Description                                      | Example    |
| ---------- | :------: | ------------------------------------------------ | ---------- |
| `messages` |    ✓     |                                                  | `[{}]`     |
| `system`   |    ✓     |                                                  | `"string"` |
| `maxUses`  |    ✗     | The maximum number of times the tool can be used | `123`      |

#### Example Snippet

```typescript
import { Client } from "api_ts";

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

[ToolsInternetSearchCreateResponse](/src/types/tools-internet-search-create-response.ts)

##### Example

```typescript
{"markdown": "string"}
```
