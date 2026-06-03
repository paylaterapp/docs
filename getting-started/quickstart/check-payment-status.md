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

# 🏳️ Check Payment Status

Track the real-time status of your payment with ease. Whether it's pending, successful, or failed, this page gives you instant visibility into where your transaction stands. No more guessing—just clear, up-to-date information to keep you in control.

## Endpoint

### Sandbox

`GET https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/status`&#x20;

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/status`&#x20;

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)

## Query Parameters

| Parameter | Type   | Required | Description     |
| --------- | ------ | -------- | --------------- |
| order\_id | String | ✅        | Unique order ID |

## Success Response (Statuses)

```
{
    "message": "Order not initiated",
    "status": 0
}

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

* `0` = customer didn't proceed
* `1` = pending
* `2` = success
* `3` = failed
