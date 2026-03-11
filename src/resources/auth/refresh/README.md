# auth.refresh

## Module Functions

### Refresh token <a name="create"></a>

**API Endpoint**: `POST /auth/refresh`

#### Parameters

| Parameter         | Required | Description | Example                      |
| ----------------- | :------: | ----------- | ---------------------------- |
| `data`            |    ✗     |             | `{"refreshToken": "string"}` |
| `└─ refreshToken` |    ✓     |             | `"string"`                   |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.auth.refresh.create();
```

#### Response

##### Type

[AuthRefreshCreateResponse](/src/types/auth-refresh-create-response.ts)

##### Example

```typescript
{"accessToken": "string", "expiresIn": 123.0, "refreshToken": "string"}
```
