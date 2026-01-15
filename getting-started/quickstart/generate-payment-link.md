# 💰 Generate Payment Link

This API allows you to generate a secure, one-time [PayLater ](https://paylaterapp.com/)payment link for a specific order. The response includes a URL that must be used to **redirect the customer to complete their** [**PayLater** ](https://paylaterapp.com/)**transaction**. Ideal for web and app checkouts where you want to initiate the [PayLater ](https://paylaterapp.com/)flow externally and return to your platform post-payment.

## Endpoint

### Sandbox

`POST https://connect-sandbox.paylaterapp.com/api/paylater/merchant-portal/web-checkout/`&#x20;

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/`&#x20;

## Headers

* `x-api-key`: Your API key (Required)
* `Content-Type`: `application/json`

## Request Body

<table data-header-hidden><thead><tr><th>Parameter</th><th>Type</th><th width="156">Required</th><th>Description</th></tr></thead><tbody><tr><td>merchantId</td><td>String</td><td>✅</td><td>Unique ID assigned to your business</td></tr><tr><td>outletId</td><td>Long</td><td>✅</td><td>Storefront or outlet identifier</td></tr><tr><td>currency</td><td>String</td><td>✅</td><td>Must be <code>QAR</code></td></tr><tr><td>amount</td><td>Double</td><td>✅</td><td>Range: 300–25,000</td></tr><tr><td>orderId</td><td>String</td><td>✅</td><td>Merchant  unique transaction identifier</td></tr><tr><td>successRedirectUrl</td><td>String</td><td>✅</td><td>URL to redirect customer on success</td></tr><tr><td>failRedirectUrl</td><td>String</td><td>✅</td><td>URL to redirect customer on failure</td></tr></tbody></table>

## Sample cURL

```
curl --location 'https://connect-sandbox.paylaterapp.com/api/paylater/merchant-portal/web-checkout/' \
--header 'x-api-key: a4f9feba-19dd-47b7-8d09-268a25c44a35' \
--header 'Content-Type: application/json' \
--data '{
  "merchantId": "138",
  "outletId": 1000000061,
  "currency": "QAR",
  "amount": 350.00,
  "orderId": "O-3445",
  "successRedirectUrl": "https://test.com/success",
  "failRedirectUrl": "https://test.com/fail"
}'
```

## Success Response

```
{
  "paymentLinkUrl": "https://payments-sandbox.paylaterapp.com/paylink/uuid?token=xyz&channel=web"
}
```

## Error Response (Example)

```
{
  "error": "Merchant ID cannot be null"
}

{
  "error": "Order ID must be unique"
}

{
  "error": "Amount must be between 300 and 4000"
}
```
