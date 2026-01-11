# tools

## Module Functions

### Get all tools <a name="list"></a>

**API Endpoint**: `GET /tools`

#### Example Snippet

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.tools.list();
```

#### Response

##### Type

[ToolsListResponse](/src/types/tools-list-response.ts)

##### Example

```typescript
{}
```

## Submodules

- [code-execution](code-execution/README.md) - code-execution
- [dictionary-search](dictionary-search/README.md) - dictionary-search
- [format](format/README.md) - format
- [internet-search](internet-search/README.md) - internet-search
- [memory-query](memory-query/README.md) - memory-query
- [meta-tagger](meta-tagger/README.md) - meta-tagger
- [standard-llm](standard-llm/README.md) - standard-llm
- [structured-output](structured-output/README.md) - structured-output
