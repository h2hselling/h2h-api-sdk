# tools.standard-llm

## Module Functions

### Run standard LLM <a name="create"></a>

Send a standard LLM request and return the model response content.

**API Endpoint**: `POST /tools/standard_llm`

#### Parameters

| Parameter              | Required | Description                              | Example                                        |
| ---------------------- | :------: | ---------------------------------------- | ---------------------------------------------- |
| `messages`             |    ✓     |                                          | `[{"content": "string", "role": "assistant"}]` |
| `system`               |    ✓     |                                          | `"string"`                                     |
| `additionalProperties` |    ✗     |                                          | `{}`                                           |
| `maxTokens`            |    ✗     | The maximum number of tokens to generate | `123`                                          |
| `model`                |    ✗     | The name of the model to use for the LLM | `"string"`                                     |
| `stopSequences`        |    ✗     | The stop sequences to use for the LLM    | `["string"]`                                   |
| `temperature`          |    ✗     | The temperature to use for the LLM       | `123.0`                                        |
| `topK`                 |    ✗     | The top k to use for the LLM             | `123`                                          |
| `topP`                 |    ✗     | The top p to use for the LLM             | `123.0`                                        |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.standardLlm.create({
  messages: [{ content: "string", role: "assistant" }],
  system: "string",
});
```

#### Response

##### Type

Array of [ToolsStandardLlmCreateResponseItem](/src/types/tools-standard-llm-create-response-item.ts)

##### Example

```typescript
[{}]
```
