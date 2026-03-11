# tools.structured-output

## Module Functions

### Structured output tool <a name="create"></a>

**API Endpoint**: `POST /tools/structured_output`

#### Parameters

| Parameter  | Required | Description                                      | Example    |
| ---------- | :------: | ------------------------------------------------ | ---------- |
| `input`    |    ✓     | the unstructured data to format                  | `"string"` |
| `schema`   |    ✓     |                                                  | `{}`       |
| `validate` |    ✗     | Whether to validate the schema against the input | `true`     |

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
