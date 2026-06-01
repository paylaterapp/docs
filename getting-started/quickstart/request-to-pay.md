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

# 💰 Request to Pay

The Request to Pay API allows merchants to initiate a payment request directly from the merchant portal or POS to a shopper's PayLater mobile app. When called, the API sends a push notification to the shopper prompting them to review and approve the transaction within their app, where they can select their preferred installment plan and complete the purchase. This endpoint is designed for in-store, phone order, and remote checkout scenarios where the shopper is not transacting through a merchant's website.

## Endpoint

### Sandbox

`POST https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/request-to-pay`&#x20;

### Production

`POST https://connect.paylaterapp.com/api/paylater/merchant-portal/request-to-pay`&#x20;

## Headers

* `x-api-key`: Your API key (Required)
* `Content-Type`: `application/json`

## Request Body

<table data-header-hidden><thead><tr><th>Parameter</th><th>Type</th><th width="156">Required</th><th>Description</th></tr></thead><tbody><tr><td>merchant_id</td><td>String</td><td>✅</td><td>Unique ID assigned to your business</td></tr><tr><td>outlet_id</td><td>Number</td><td>✅</td><td>Storefront or outlet identifier</td></tr><tr><td>mobile_number</td><td>String</td><td>✅</td><td>Registered Customer mobile number</td></tr><tr><td>order_amount</td><td>Decimal</td><td>✅</td><td>Requested payment amount</td></tr><tr><td>merchant_order_reference</td><td>String</td><td>✅</td><td>Merchant  unique transaction identifier</td></tr><tr><td>expiry_minutes</td><td>Integer</td><td>✅</td><td>Expiry time in minutes</td></tr></tbody></table>

## Sample cURL

```
curl --location 'https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/request-to-pay' \
--header 'x-api-key: a4f9feba-19dd-47b7-8d09-268a25c44a35' \
--header 'Content-Type: application/json' \
--data '{
    "merchant_id": "138",
    "outlet_id": 1000000061,
    "mobile_number": "97451118021",
    "order_amount": 3015,
    "merchant_order_reference": "ORD-5",
    "expiry_minutes": 20
}'
```

## Success Response

```
{
    "merchant_order_reference": "ORD-5",
    "status": "SUCCESS",
    "expiry_date": "2026-04-28T10:15:41.477013291"
}
```

## Error Response (Example)

```
{
    "status": "FAILED",
    "message": "A Request-to-Pay already exists for this merchant order reference.",
    "http_code": 409,
    "error_reference": "RTP-409-DUPLICATE-REFERENCE"
}

{
    "status": "FAILED",
    "message": "Unable to process Request-to-Pay right now. Please try again later.",
    "http_code": 404,
    "error_reference": "RTP-UPSTREAM-ERROR"
}
```
