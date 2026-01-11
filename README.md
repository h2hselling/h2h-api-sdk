# Human 2 Human API - Typescript

api (1.0.0)

## Getting Started

#### Example Client Initialization

```typescript
import Client from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
```

## Module Documentation and Snippets

### [agent.build.workflow](src/resources/agent/build/workflow/README.md)

- [create](src/resources/agent/build/workflow/README.md#create) - Build a workflow
- [list](src/resources/agent/build/workflow/README.md#list) - Get the output of a workflow

### [auth.login](src/resources/auth/login/README.md)

- [create](src/resources/auth/login/README.md#create) - Get token

### [auth.refresh](src/resources/auth/refresh/README.md)

- [create](src/resources/auth/refresh/README.md#create) - Refresh token

### [chats](src/resources/chats/README.md)

- [create](src/resources/chats/README.md#create) - Create a chat
- [get](src/resources/chats/README.md#get) - Get a chat
- [patch](src/resources/chats/README.md#patch) - Continue a chat

### [feeds](src/resources/feeds/README.md)

- [create](src/resources/feeds/README.md#create) - Create a new feed
- [get](src/resources/feeds/README.md#get) - Get a specific feed by ID
- [list](src/resources/feeds/README.md#list) - List all feeds

### [feeds.items](src/resources/feeds/items/README.md)

- [create](src/resources/feeds/items/README.md#create) - Create a new feed item for an API feed
- [get](src/resources/feeds/items/README.md#get) - Get a specific feed item by ID

### [feeds.vector.search](src/resources/feeds/vector/search/README.md)

- [create](src/resources/feeds/vector/search/README.md#create) - Run a query against feed embeddings

### [integrations.api](src/resources/integrations/api/README.md)

- [create](src/resources/integrations/api/README.md#create) - Create a new API integration
- [delete](src/resources/integrations/api/README.md#delete) - Delete an API integration
- [get](src/resources/integrations/api/README.md#get) - Get an API integration by ID

### [integrations.api.operations](src/resources/integrations/api/operations/README.md)

- [create](src/resources/integrations/api/operations/README.md#create) - Create a new API operation
- [delete](src/resources/integrations/api/operations/README.md#delete) - Delete an API operation
- [get](src/resources/integrations/api/operations/README.md#get) - Get an API operation by ID
- [patch](src/resources/integrations/api/operations/README.md#patch) - Update an API operation

### [integrations.api.secrets](src/resources/integrations/api/secrets/README.md)

- [create](src/resources/integrations/api/secrets/README.md#create) - Create a new API secret
- [delete](src/resources/integrations/api/secrets/README.md#delete) - Delete an API secret
- [list](src/resources/integrations/api/secrets/README.md#list) - Get all API secrets for an API integration

### [searchGroups](src/resources/search-groups/README.md)

- [create](src/resources/search-groups/README.md#create) - Create a new dictionary
- [get](src/resources/search-groups/README.md#get) - Get a search group by id
- [list](src/resources/search-groups/README.md#list) - List search groups

### [searchGroups.items](src/resources/search-groups/items/README.md)

- [create](src/resources/search-groups/items/README.md#create) - Create a new search item in a search group
- [get](src/resources/search-groups/items/README.md#get) - Get a search item by id
- [list](src/resources/search-groups/items/README.md#list) - List search items in a search group

### [tools](src/resources/tools/README.md)

- [list](src/resources/tools/README.md#list) - Get all tools

### [tools.codeExecution](src/resources/tools/code-execution/README.md)

- [create](src/resources/tools/code-execution/README.md#create) - Execute code and return the result

### [tools.dictionarySearch](src/resources/tools/dictionary-search/README.md)

- [create](src/resources/tools/dictionary-search/README.md#create) - Search for dictionary definitions related to a feed item

### [tools.format](src/resources/tools/format/README.md)

- [create](src/resources/tools/format/README.md#create) - Format an input into HTML or Markdown

### [tools.internetSearch](src/resources/tools/internet-search/README.md)

- [create](src/resources/tools/internet-search/README.md#create) - Internet search tool

### [tools.memoryQuery](src/resources/tools/memory-query/README.md)

- [create](src/resources/tools/memory-query/README.md#create) - Query the memory table

### [tools.metaTagger](src/resources/tools/meta-tagger/README.md)

- [create](src/resources/tools/meta-tagger/README.md#create) - Meta Tag a feed item

### [tools.standardLlm](src/resources/tools/standard-llm/README.md)

- [create](src/resources/tools/standard-llm/README.md#create) - Standard LLM tool

### [tools.structuredOutput](src/resources/tools/structured-output/README.md)

- [create](src/resources/tools/structured-output/README.md#create) - Structured output tool

### [workflow.run.trigger](src/resources/workflow/run/trigger/README.md)

- [create](src/resources/workflow/run/trigger/README.md#create) - Trigger a new workflow run

### [workflows.dispatch](src/resources/workflows/dispatch/README.md)

- [create](src/resources/workflows/dispatch/README.md#create) - Dispatch a new workflow run. This is an asynchronous call that will return the workflow run ID and allow you to poll for the result.

### [workflows.invoke](src/resources/workflows/invoke/README.md)

- [create](src/resources/workflows/invoke/README.md#create) - Invoke a new workflow run. This is a synchronous call that will wait for the workflow run to complete and return the result.

<!-- MODULE DOCS END -->
