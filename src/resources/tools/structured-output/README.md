# tools.structured-output

## Module Functions

### Generate structured output <a name="create"></a>

Transform unstructured input into JSON that matches the provided schema.

**API Endpoint**: `POST /tools/structured_output`

#### Parameters

| Parameter          | Required | Description                                      | Example      |
| ------------------ | :------: | ------------------------------------------------ | ------------ |
| `input`            |    ✓     | the unstructured data to format                  | `"string"`   |
| `schema`           |    ✓     |                                                  | `{}`         |
| `params`           |    ✗     |                                                  | `{}`         |
| `└─ maxTokens`     |    ✗     | The maximum number of tokens to generate         | `123`        |
| `└─ model`         |    ✗     | The name of the model to use for the LLM         | `"string"`   |
| `└─ stopSequences` |    ✗     | The stop sequences to use for the LLM            | `["string"]` |
| `└─ temperature`   |    ✗     | The temperature to use for the LLM               | `123.0`      |
| `└─ topK`          |    ✗     | The top k to use for the LLM                     | `123`        |
| `└─ topP`          |    ✗     | The top p to use for the LLM                     | `123.0`      |
| `validate`         |    ✗     | Whether to validate the schema against the input | `true`       |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.structuredOutput.create({
  input: "string",
  schema: {},
});
```
