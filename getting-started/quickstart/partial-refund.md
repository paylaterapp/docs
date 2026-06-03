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

# 💸 Partial Refund

Initiate a partial refund for a completed transaction using the Partial Refund API. This endpoint allows you to seamlessly return funds to the shopper while keeping records updated for reconciliation and reporting purposes.

## Endpoint

### Sandbox

`POST https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/refund`

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/refund`

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)
* `Content-Type`: `application/json`

## Request Body

| Parameter | Type   | Required | Description                                           |
| --------- | ------ | -------- | ----------------------------------------------------- |
| order\_id | String | ✅        | Your merchant ID                                      |
| amount    | String | ✅        | Partial amount. Should be less than total order value |

## Success Response

```
{
  "message": "Partial Refund request accepted for reference Id: 0-4756"
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

{
  "error": "Refund Error",
  "message": "Invalid Transaction type."
}
```

***

For questions, support, or sandbox access — reach out to your PayLater account manager.

Ready to go? Start coding. 🛠️
