# auth.login

## Module Functions

### Get token <a name="create"></a>

**API Endpoint**: `POST /auth/login`

#### Parameters

| Parameter     | Required | Description | Example                                     |
| ------------- | :------: | ----------- | ------------------------------------------- |
| `data`        |    ✗     |             | `{"email": "string", "password": "string"}` |
| `└─ email`    |    ✓     |             | `"string"`                                  |
| `└─ password` |    ✓     |             | `"string"`                                  |

#### Example Snippet

```typescript
import { Client } from "api_ts";

const client = new Client({
  apiKey: process.env["API_KEY"]!!,
  token: process.env["API_TOKEN"]!!,
});
const res = await client.auth.login.create();
```

#### Response

##### Type

[AuthLoginCreateResponse](/src/types/auth-login-create-response.ts)

##### Example

```typescript
{"accessToken": "string", "expiresIn": 123.0, "refreshToken": "string"}
```
