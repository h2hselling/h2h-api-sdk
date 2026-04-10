# tools.internet-search

## Module Functions

### Run internet search <a name="create"></a>

Use the internet search tool to answer a prompt with live web search support.

**API Endpoint**: `POST /tools/internet_search`

#### Parameters

| Parameter       | Required | Description                                      | Example                                        |
| --------------- | :------: | ------------------------------------------------ | ---------------------------------------------- |
| `messages`      |    ✓     |                                                  | `[{"content": "string", "role": "assistant"}]` |
| `system`        |    ✓     |                                                  | `"string"`                                     |
| `maxTokens`     |    ✗     | The maximum number of tokens to generate         | `123`                                          |
| `maxUses`       |    ✗     | The maximum number of times the tool can be used | `123`                                          |
| `model`         |    ✗     | The name of the model to use for the LLM         | `"string"`                                     |
| `stopSequences` |    ✗     | The stop sequences to use for the LLM            | `["string"]`                                   |
| `temperature`   |    ✗     | The temperature to use for the LLM               | `123.0`                                        |
| `topK`          |    ✗     | The top k to use for the LLM                     | `123`                                          |
| `topP`          |    ✗     | The top p to use for the LLM                     | `123.0`                                        |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.internetSearch.create({
  messages: [{ content: "string", role: "assistant" }],
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
