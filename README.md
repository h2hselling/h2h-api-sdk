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
- [list](src/resources/agent/build/workflow/README.md#list) - Get workflow build output

### [auth.login](src/resources/auth/login/README.md)

- [create](src/resources/auth/login/README.md#create) - Log in

### [auth.refresh](src/resources/auth/refresh/README.md)

- [create](src/resources/auth/refresh/README.md#create) - Refresh an auth token

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

### [memory.tables](src/resources/memory/tables/README.md)

- [create](src/resources/memory/tables/README.md#create) - Create a memory table
- [delete](src/resources/memory/tables/README.md#delete) - Delete a memory table
- [get](src/resources/memory/tables/README.md#get) - Get a memory table
- [list](src/resources/memory/tables/README.md#list) - List memory tables

### [memory.tables.mutate](src/resources/memory/tables/mutate/README.md)

- [create](src/resources/memory/tables/mutate/README.md#create) - Mutate a memory table

### [memory.tables.query](src/resources/memory/tables/query/README.md)

- [create](src/resources/memory/tables/query/README.md#create) - Query a memory table

### [searchGroups](src/resources/search-groups/README.md)

- [create](src/resources/search-groups/README.md#create) - Create a new dictionary
- [get](src/resources/search-groups/README.md#get) - Get a search group by id
- [list](src/resources/search-groups/README.md#list) - List search groups

### [searchGroups.items](src/resources/search-groups/items/README.md)

- [create](src/resources/search-groups/items/README.md#create) - Create a new search item in a search group
- [get](src/resources/search-groups/items/README.md#get) - Get a search item by id
- [list](src/resources/search-groups/items/README.md#list) - List search items in a search group

### [subscriptions.events](src/resources/subscriptions/events/README.md)

- [create](src/resources/subscriptions/events/README.md#create) - Create an event subscription
- [delete](src/resources/subscriptions/events/README.md#delete) - Delete an event subscription
- [get](src/resources/subscriptions/events/README.md#get) - Get an event subscription
- [list](src/resources/subscriptions/events/README.md#list) - List event subscriptions

### [tools](src/resources/tools/README.md)

- [list](src/resources/tools/README.md#list) - List tools

### [tools.codeExecution](src/resources/tools/code-execution/README.md)

- [create](src/resources/tools/code-execution/README.md#create) - Execute code

### [tools.dictionarySearch](src/resources/tools/dictionary-search/README.md)

- [create](src/resources/tools/dictionary-search/README.md#create) - Search dictionary definitions

### [tools.format](src/resources/tools/format/README.md)

- [create](src/resources/tools/format/README.md#create) - Format content

### [tools.internetSearch](src/resources/tools/internet-search/README.md)

- [create](src/resources/tools/internet-search/README.md#create) - Run internet search

### [tools.memoryQuery](src/resources/tools/memory-query/README.md)

- [create](src/resources/tools/memory-query/README.md#create) - Query memory

### [tools.metaTagger](src/resources/tools/meta-tagger/README.md)

- [create](src/resources/tools/meta-tagger/README.md#create) - Apply meta tags

### [tools.standardLlm](src/resources/tools/standard-llm/README.md)

- [create](src/resources/tools/standard-llm/README.md#create) - Run standard LLM

### [tools.structuredOutput](src/resources/tools/structured-output/README.md)

- [create](src/resources/tools/structured-output/README.md#create) - Generate structured output

### [workflows](src/resources/workflows/README.md)

- [create](src/resources/workflows/README.md#create) - Create a workflow
- [delete](src/resources/workflows/README.md#delete) - Delete a workflow
- [get](src/resources/workflows/README.md#get) - Get a workflow
- [list](src/resources/workflows/README.md#list) - List workflows
- [patch](src/resources/workflows/README.md#patch) - Update a workflow

### [workflows.dispatch](src/resources/workflows/dispatch/README.md)

- [create](src/resources/workflows/dispatch/README.md#create) - Dispatch a workflow

### [workflows.invoke](src/resources/workflows/invoke/README.md)

- [create](src/resources/workflows/invoke/README.md#create) - Invoke a workflow

### [workflows.runs](src/resources/workflows/runs/README.md)

- [create](src/resources/workflows/runs/README.md#create) - Create a workflow run
- [delete](src/resources/workflows/runs/README.md#delete) - Delete a workflow run
- [get](src/resources/workflows/runs/README.md#get) - Get a workflow run
- [list](src/resources/workflows/runs/README.md#list) - List workflow runs

### [workflows.runs.dispatch](src/resources/workflows/runs/dispatch/README.md)

- [create](src/resources/workflows/runs/dispatch/README.md#create) - Dispatch a workflow run

### [workflows.versions](src/resources/workflows/versions/README.md)

- [create](src/resources/workflows/versions/README.md#create) - Create a workflow version
- [delete](src/resources/workflows/versions/README.md#delete) - Delete a workflow version
- [get](src/resources/workflows/versions/README.md#get) - Get a workflow version
- [list](src/resources/workflows/versions/README.md#list) - List workflow versions
- [patch](src/resources/workflows/versions/README.md#patch) - Update a workflow version

<!-- MODULE DOCS END -->
