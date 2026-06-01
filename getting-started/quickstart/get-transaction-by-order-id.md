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

# 💵 Get Transaction by Order ID

Retrieve full transaction details using a specific Order ID. This endpoint provides real-time insights into the payment status, shopper info, transaction amount, and timestamps—ideal for quick lookups, reconciliations, or support queries.

## Endpoint

### Sandbox

`GET https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/web-checkout/transactions/{order_id}?merchantId={{merchantID}}`&#x20;

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/transactions/{order_id}?merchantId={{merchantID}}`&#x20;

## Headers

* `x-api-key`: Your API key (Required)

## Query Parameters

| merchantId | String | ✅ | Your merchant ID         |
| ---------- | ------ | - | ------------------------ |
| order\_id  | String | ✅ | Merchant Unique order ID |

## Success Response

```
{
  "id": 10129,
  "customer": {
    "fullName": "JOHN SMITH",
    "mobileNumber": "97466955189",
    "email": "john@test.com",
    "allowedSpendingLimit": "25000.0"
  },
  "loan": {
    "emi": 154.75,
    "grantedAmount": 619.00,
    "installmentAmount": 154.75,
    "noOfTerms": 4
  },
  "orderStatus": {
    "message": "pending",
    "status": 1
  }
}
```

## Error Responses

```
{
  "message": "Order not initiated"
}

{
  "message": "Order ID not found"
}
```
