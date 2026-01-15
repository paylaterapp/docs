# 📃 Webhook Integration

## Overview

The [PayLater ](https://paylaterapp.com/)system sends real-time webhook notifications to your backend when key events occur, such as transaction status updates. This ensures your platform stays in sync with the latest [PayLater ](https://paylaterapp.com/)events.

⚠️ **Important:** To activate webhooks, merchants must share their **Webhook Endpoint URL** with [PayLater](https://paylaterapp.com/) and request their unique **Webhook Secret** from their account manager.

## 📥 Webhook Request

Webhook events are delivered as an HTTP `POST` request with a JSON payload.

## Endpoint

You must expose a public POST endpoint to receive these requests.&#x20;

## Headers

* `Content-Type: application/json`

## Request Body

```
{
  "merchantId": "<merchant_id>",
  "orderId": "<order_id>",
  "paylaterRef": "PL1746499849330726",
  "status": "<status>",
  "timestamp": "<timestamp>",
  "signature": "<signature>",
  "txHash": "<tx_hash>",
  "comments": "<comments>"
}
```

### Parameter Descriptions

| Field      | Type   | Description                                                                                      |
| ---------- | ------ | ------------------------------------------------------------------------------------------------ |
| merchantId | String | Unique identifier for the merchant                                                               |
| orderId    | String | Unique identifier for the order                                                                  |
| status     | String | Status of the order (e.g., `success`, `failed`, `pending`)                                       |
| timestamp  | Long   | Epoch timestamp of the request                                                                   |
| signature  | String | HMAC SHA-256 signature generated using `txHash` and the webhook secret                           |
| txHash     | String | MD5 hash of the concatenated payload (merchantId + orderId + orderstatus + timestamp + comments) |
| comments   | String | Optional comments or metadata                                                                    |

## 🔐 Security & Validation

To validate the webhook and ensure it's sent by PayLater:

1. **Reconstruct the Data String:**
   * Concatenate `merchantId + orderId + status + timestamp + comments`
   * Convert the whole string to uppercase
   * Generate an MD5 hash of this string and compare it with the provided `txHash`
2. **Validate Signature:**
   * Use HMAC SHA-256 with your `merchantWebhookSecret`
   * Hash the `txHash` value
   * Compare the result with the `signature` field from the request

## ✅ Sample Node.js Verification

```
const crypto = require('crypto');

const verifyWebhook = (req) => {
  const { merchantId, orderId, status, timestamp, txHash, signature, comments } = req.body;
  const data = `${merchantId}${orderId}${status}${timestamp}${comments}`.toUpperCase();
  const computedTxHash = crypto.createHash('md5').update(data).digest('hex');
  if (computedTxHash !== txHash) return false;
  const computedSignature = crypto.createHmac('sha256', process.env.WEBHOOK_SECRET)
                                  .update(txHash)
                                  .digest('hex');
  return computedSignature === signature;
};
```

## ✅ Sample PHP Verification

```
$MERCHANT_SECRET = "your_webhook_secret";
$request = json_decode(file_get_contents("php://input"), true);
$dataString = strtoupper($request['merchantId'] . $request['orderId'] . $request['status'] . $request['timestamp'] . $request['comments']);
$computedTxHash = md5($dataString);
$computedSignature = hash_hmac("sha256", $computedTxHash, $MERCHANT_SECRET);
if ($computedSignature === $request['signature']) {
  http_response_code(200);
  echo json_encode(["message" => "Webhook received successfully"]);
} else {
  http_response_code(403);
  echo json_encode(["message" => "Invalid signature"]);
}
```

***
