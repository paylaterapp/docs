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

# 👥 Get Shopper Information

Quickly check if a customer is a registered [PayLater ](https://paylaterapp.com/)shopper. This tool returns their shopper status along with their assigned credit limit and available balance—perfect for verifying eligibility before proceeding with a transaction.

## Endpoint

### Sandbox

`GET https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/shopper`&#x20;

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/shopper`&#x20;

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)

## Query Parameters

| Parameter      | Type   | Required | Description             |
| -------------- | ------ | -------- | ----------------------- |
| mobile\_number | String | ✅        | Shopper's mobile number |
| email          | String | ✅        | Shopper's email address |

## Sample Success Response

```
{
  "shopperId": "uuid",
  "email": "test@sample.com",
  "mobileNumber": "97412345678",
  "currentSpendingLimit": 925.0,
  "allowedSpendingLimit": 4000.0
}
```

## Error Responses

```
{
  "message": "Shopper not found"
}

{
  "message": "Missing API key in request headers"
}
```

***

###
