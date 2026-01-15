# 💸 Refund API

Initiate a full refund for a completed transaction using the Refund API. This endpoint allows you to seamlessly return funds to the shopper while keeping records updated for reconciliation and reporting purposes.

## Endpoint

### Sandbox

`GET https://connect-sandbox.paylaterapp.com/api/paylater/merchant-portal/web-checkout/refund`

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/refund`

## Headers

* `x-api-key`: Your API key (Required)

## Query Parameters

<table data-header-hidden><thead><tr><th></th><th></th><th width="160.8203125"></th><th></th></tr></thead><tbody><tr><td>Parameter</td><td>Type</td><td>Required</td><td>Description</td></tr><tr><td>merchantId</td><td>String</td><td>✅</td><td>Your merchant ID</td></tr><tr><td>transactionReference</td><td>String</td><td>✅</td><td>Merchant Order ID</td></tr><tr><td>transactionType</td><td>String</td><td>✅</td><td>Must be <code>DOWN_PAYMENT</code></td></tr></tbody></table>

## Success Response

```
{
  "message": "Refund request accepted for reference Id: PL1740851963584963"
}
```

## Error Responses

```
{
  "error": "Transaction Reference is required"
}

{
  "error": "Transaction Type is required"
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
