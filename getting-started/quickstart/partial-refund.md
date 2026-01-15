# 💸 Partial Refund

Initiate a partial refund for a completed transaction using the Partial Refund API. This endpoint allows you to seamlessly return funds to the shopper while keeping records updated for reconciliation and reporting purposes.

## Endpoint

### Sandbox

`POST https://connect-sandbox.paylaterapp.com/api/paylater/merchant-portal/web-checkout/refund/partial`

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/refund/partial`

## Headers

* `x-api-key`: Your API key (Required)

## Query Parameters

| Parameter            | Type   | Required | Description       |
| -------------------- | ------ | -------- | ----------------- |
| merchantId           | String | ✅        | Your merchant ID  |
| transactionReference | String | ✅        | PayLater Order ID |

## Request Body

<table data-header-hidden><thead><tr><th>Parameter</th><th>Type</th><th width="156">Required</th><th>Description</th></tr></thead><tbody><tr><td>amount</td><td>String</td><td>✅</td><td>Partial amount. Should be less than total order value</td></tr></tbody></table>

## Sample cURL

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
