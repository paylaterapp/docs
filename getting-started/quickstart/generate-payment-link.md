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

# 💰 Generate Payment Link

This API allows you to generate a secure, one-time [PayLater ](https://paylaterapp.com/)payment link for a specific order. The response includes a URL that must be used to **redirect the customer to complete their** [**PayLater** ](https://paylaterapp.com/)**transaction**. Ideal for web and app checkouts where you want to initiate the [PayLater ](https://paylaterapp.com/)flow externally and return to your platform post-payment.

## Endpoint

### Sandbox

`POST https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout`&#x20;

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout`&#x20;

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)
* `Content-Type`: `application/json`

## Request Body

<table><thead><tr><th>Parameter</th><th>Type</th><th width="156">Required</th><th>Description</th></tr></thead><tbody><tr><td>outlet_id</td><td>Long</td><td>✅</td><td>Storefront or outlet identifier</td></tr><tr><td>currency</td><td>String</td><td>✅</td><td>Must be <code>QAR</code></td></tr><tr><td>amount</td><td>Double</td><td>✅</td><td>Range: 300–25,000</td></tr><tr><td>order_id</td><td>String</td><td>✅</td><td>Merchant  unique transaction identifier</td></tr><tr><td>success_redirect_url</td><td>String</td><td>✅</td><td>URL to redirect customer on success</td></tr><tr><td>fail_redirect_url</td><td>String</td><td>✅</td><td>URL to redirect customer on failure</td></tr><tr><td><p></p><p>expiry_duration</p></td><td>Integer</td><td>✅</td><td>Expiry limit for link 1 to 1440 minutes</td></tr></tbody></table>

## Sample cURL

<pre><code>curl --location 'https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout' \
<strong>--header 'Authorization: Bearer ey********hg' \
</strong>--header 'Content-Type: application/json' \
--data '{
  "outlet_id": 1000000061,
  "currency": "QAR",
  "amount": 350.00,
  "order_id": "O-3445",
  "success_redirect_url": "https://test.com/success",
  "fail_redirect_url": "https://test.com/fail",
  "expiry_duration": 10
}'
</code></pre>

## Success Response

```
{
  "paymentLinkUrl": "https://payments.uat.paylaterapp.com/paylink/uuid?token=xyz&channel=web"
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
