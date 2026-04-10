# tools.format

## Module Functions

### Format content <a name="create"></a>

Format an input string into HTML or Markdown using the formatting tool.

**API Endpoint**: `POST /tools/format`

#### Parameters

| Parameter              | Required | Description                              | Example      |
| ---------------------- | :------: | ---------------------------------------- | ------------ |
| `format`               |    ✓     | Desired output format                    | `"html"`     |
| `input`                |    ✓     | Input to format                          | `"string"`   |
| `instructions`         |    ✓     | Instructions for the formatter           | `"string"`   |
| `additionalProperties` |    ✗     |                                          | `{}`         |
| `params`               |    ✗     |                                          | `{}`         |
| `└─ maxTokens`         |    ✗     | The maximum number of tokens to generate | `123`        |
| `└─ model`             |    ✗     | The name of the model to use for the LLM | `"string"`   |
| `└─ stopSequences`     |    ✗     | The stop sequences to use for the LLM    | `["string"]` |
| `└─ temperature`       |    ✗     | The temperature to use for the LLM       | `123.0`      |
| `└─ topK`              |    ✗     | The top k to use for the LLM             | `123`        |
| `└─ topP`              |    ✗     | The top p to use for the LLM             | `123.0`      |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.format.create({
  format: "html",
  input: "string",
  instructions: "string",
});
```

#### Response

##### Type

Array of [ToolsFormatCreateResponseItem](/src/types/tools-format-create-response-item.ts)

##### Example

```typescript
[{}]
```
