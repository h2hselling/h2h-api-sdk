# tools.format

## Module Functions

### Format an input into HTML or Markdown <a name="create"></a>

**API Endpoint**: `POST /tools/format`

#### Parameters

| Parameter              | Required | Description                    | Example    |
| ---------------------- | :------: | ------------------------------ | ---------- |
| `format`               |    ✓     | Desired output format          | `"html"`   |
| `input`                |    ✓     | Input to format                | `"string"` |
| `instructions`         |    ✓     | Instructions for the formatter | `"string"` |
| `additionalProperties` |    ✗     |                                | `{}`       |

#### Example Snippet

```typescript
import Client from "api_ts";

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
