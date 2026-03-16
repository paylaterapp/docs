# 💲 Get Transactions List

Fetch a comprehensive list of all transactions linked to your account. Filter by date, status, or shopper to easily monitor activity, track performance, and streamline reconciliation—all in one place.

## Endpoint

### Sandbox

`GET https://`connect.uat.paylaterapp`.com/api/paylater/merchant-portal/web-checkout/transactions`

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/web-checkout/transactions`&#x20;

## Headers

* `x-api-key`: Your API key (Required)

## Query Parameters

| merchantId | String | ✅ | Your merchant ID                           |
| ---------- | ------ | - | ------------------------------------------ |
| size       | Int    | ✅ | Number of records per page                 |
| page       | Int    | ✅ | Page number                                |
| searchText | String | ❌ | Search keyword for customer name, ID, etc. |
| startDate  | Date   | ❌ | Start date filter (YYYY-MM-DD)             |
| endDate    | Date   | ❌ | End date filter (YYYY-MM-DD)               |
| status     | String | ❌ | Transaction status                         |

## Success Response

A paginated list of transactions with customer, loan, and status details.

## Error Responses

```
{
  "error": "Merchant ID is required"
}

{
  "error": "Invalid API Key"
}
```
