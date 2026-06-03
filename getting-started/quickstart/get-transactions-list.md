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

# 💲 Get Transactions List

Fetch a comprehensive list of all transactions linked to your account. Filter by date, status, or shopper to easily monitor activity, track performance, and streamline reconciliation—all in one place.

## Endpoint

### Sandbox

`GET https://connect.uat.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/transactions`&#x20;

### Production

`GET https://connect.paylaterapp.com/api/paylater/merchant-portal/v2/web-checkout/transactions`&#x20;

## Headers

* `Authorization`: Bearer \{{bearer\_token\}} Your Access Token (Required)

## Query Parameters

| size         | Int    | ✅ | Number of records per page                 |
| ------------ | ------ | - | ------------------------------------------ |
| page         | Int    | ✅ | Page number                                |
| search\_text | String | ❌ | Search keyword for customer name, ID, etc. |
| start\_date  | Date   | ❌ | Start date filter (YYYY-MM-DD)             |
| end\_date    | Date   | ❌ | End date filter (YYYY-MM-DD)               |
| status       | String | ❌ | Transaction status                         |

## Success Response

A paginated list of transactions with customer, loan, and status details.

## Error Responses

```
{
  "error": "Invalid API Key"
}
```
