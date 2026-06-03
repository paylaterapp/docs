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

# 💸 Refund API

Initiate a full refund for a completed transaction using the Refund API. This endpoint allows you to seamlessly return funds to the shopper while keeping records updated for reconciliation and reporting purposes.

## Endpoint

### Sandbox

`POST https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/refund`

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/refund`

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)
* `Content-Type`: `application/json`

## Request Body

<table><thead><tr><th>Parameter</th><th>Type</th><th width="160.8203125">Required</th><th>Description</th></tr></thead><tbody><tr><td>order_id</td><td>String</td><td>✅</td><td>Merchant Order ID</td></tr></tbody></table>

## Success Response

```
{
  "message": "Refund request accepted for reference Id: ORD-TEST-1"
}
```

## Error Responses

```
{
  "error": "Transaction Reference is required"
}

{
  "error": "Invalid API Key"
}

{
  "error": "Refund Error",
  "message": "Order cannot be refunded as it happened more than 29 days ago."
}

{
  "error": "Refund Error",
  "message": "Order contains transactions other than down payment and cannot be refunded."
}

{
  "error": "Refund Error",
  "message": "Transaction happened less than 10 minutes ago. Please try again later."
}

{
  "error": "Refund Error",
  "message": "Invalid Transaction Reference."
}
```

***

For questions, support, or sandbox access — reach out to your PayLater account manager.

Ready to go? Start coding. 🛠️
