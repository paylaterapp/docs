---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# 🔑 Get Access Token

This API allows you to generate a secure, access token via the Keyclock Token Endpoint. The response includes a access token that need to call apis for **complete their** [**PayLater** ](https://paylaterapp.com/)**transaction**. Ideal for web and app checkouts where you want to initiate the [PayLater ](https://paylaterapp.com/)flow.

## Endpoint

### Sandbox

`POST https://connect.uat.paylaterapp.com/auth/realms/api/protocol/openid-connect/token`&#x20;

### Production

`POST https://connect.paylaterapp.com/auth/realms/api/protocol/openid-connect/token`&#x20;

## Headers

* `Content-Type`: `application/x-www-form-urlencoded`

## Request Body

<table><thead><tr><th>Parameter</th><th>Type</th><th width="156">Required</th><th>Description</th></tr></thead><tbody><tr><td>grant_type</td><td>String</td><td>✅</td><td>client_credentials   "keep it same"</td></tr><tr><td>client_id</td><td>Long</td><td>✅</td><td>client_id</td></tr><tr><td>client_secret</td><td>String</td><td>✅</td><td>client_secret</td></tr></tbody></table>

## Sample cURL

```
curl --location 'https://connect.uat.paylaterapp.com/auth/realms/api/protocol/openid-connect/token' \
--header 'x-api-key: a4f9feba-19dd-47b7-8d09-268a25c44a35' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=client_credentials' \
--data-urlencode 'client_id={{merchant_client_id}}' \
--data-urlencode 'client_secret={{merchant_client_secret}}'
```

## Success Response

```
{
    "access_token": "ey***********Dw",
    "expires_in": 300,
    "refresh_expires_in": 1800,
    "refresh_token": "ey**********kQ",
    "token_type": "Bearer",
    "not-before-policy": 0,
    "session_state": "ff**********65",
    "scope": "profile email"
}
```

## Error Response (Example)

```
{
    "error": "invalid_client",
    "error_description": "Invalid client or Invalid client credentials"
}

{
    "error": "unsupported_grant_type",
    "error_description": "Unsupported grant_type"
}
```

## Token Life-cycle Implementation

1. Application starts Fetch access token (client\_credentials grant)\
   └─► Cache: { access\_token, refresh\_token, expiry = now + expires\_in }
2. Before each API call\
   ├─ If now < expiry - 60s → use cached access\_token\
   ├─ Else if refresh\_token valid → refresh\_token grant (new access\_token)\
   ├─ Else client\_credentials grant (full re-auth)
3. If your integration serves multiple outlets, you only need one token per\
   merchant (not per outlet). outlet\_id is passed per request in the body, not\
   in the token. Use the refresh\_token grant to renew tokens efficiently.

NOTE: Token caching: Cache the access token and reuse it until \~60 seconds before expiry. Use the refresh\_token grant to obtain a new access token without re-sending client credentials. Only fall back to client\_credentials if the refresh token has also expired. Do not request a new token on every API call.
