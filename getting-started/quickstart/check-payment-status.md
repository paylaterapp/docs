# 🏳️ Check Payment Status

Track the real-time status of your payment with ease. Whether it's pending, successful, or failed, this page gives you instant visibility into where your transaction stands. No more guessing—just clear, up-to-date information to keep you in control.

## Endpoint

### Sandbox

`GET https://connect-sandbox.paylaterapp.com/api/paylater/merchant-portal/web-checkout/status`

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/status`&#x20;

## Headers

* `x-api-key`: Your API key (Required)

## Query Parameters

| orderId    | String | ✅ | Unique order ID  |
| ---------- | ------ | - | ---------------- |
| merchantId | String | ✅ | Your merchant ID |

## Success Response (Statuses)

```
{
  "payLaterOrderId": "PL1744792493935483",
  "message": "pending",
  "merchantReference": "000072152",
  "status": 1
}

{
  "payLaterOrderId": "PL1744792493935483",
  "message": "success",
  "merchantReference": "000072152",
  "status": 2
}

{
  "payLaterOrderId": "PL1744792493935483",
  "message": "failed",
  "merchantReference": "000072152",
  "status": 3
}
```

## Error Response

```
{
  "error": "Order ID is required"
}
```

### **Status Codes:**

* `1` = pending
* `2` = success
* `3` = failed
