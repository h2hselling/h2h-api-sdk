# tools.standard-llm

## Module Functions

### Standard LLM tool <a name="create"></a>

**API Endpoint**: `POST /tools/standard_llm`

#### Parameters

| Parameter              | Required | Description | Example    |
| ---------------------- | :------: | ----------- | ---------- |
| `messages`             |    ✓     |             | `[{}]`     |
| `system`               |    ✓     |             | `"string"` |
| `additionalProperties` |    ✗     |             | `{}`       |

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.standardLlm.create({
  messages: [{}],
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
