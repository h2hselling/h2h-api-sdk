# tools.code-execution

## Module Functions

### Execute code <a name="create"></a>

Execute code in a supported language and return logs, structured outputs, and the final result.

**API Endpoint**: `POST /tools/code_execution`

#### Parameters

| Parameter              | Required | Description                                                                     | Example        |
| ---------------------- | :------: | ------------------------------------------------------------------------------- | -------------- |
| `code`                 |    ✓     | The source code snippet to be executed.                                         | `"string"`     |
| `inputs`               |    ✓     | An object of key-value pairs to be passed as inputs to the code.                | `{}`           |
| `language`             |    ✓     | The programming language of the code.                                           | `"javascript"` |
| `additionalProperties` |    ✗     |                                                                                 | `{}`           |
| `context`              |    ✗     | An object of key-value pairs to be passed as context to the code.               | `{}`           |
| `environment`          |    ✗     | An object of key-value pairs to be passed as environment variables to the code. | `{}`           |
| `libraries`            |    ✗     | An optional list of external libraries or packages used by the code.            | `["string"]`   |
| `outputId`             |    ✗     | The ID of the Workflow Task Output associated with the code execution           | `"string"`     |
| `taskId`               |    ✗     | The ID of the Workflow Task associated with the code execution                  | `"string"`     |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.codeExecution.create({
  code: "string",
  inputs: {},
  language: "javascript",
});
```

#### Response

##### Type

[ToolsCodeExecutionCreateResponse](/src/types/tools-code-execution-create-response.ts)

##### Example

```typescript
{"code": "string", "logs": {"stderr": ["string"], "stdout": ["string"]}, "result": {"type": "array", "value": {}}, "results": [{}]}
```
