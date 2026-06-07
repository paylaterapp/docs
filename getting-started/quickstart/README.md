---
description: >-
  The PayLater API is your gateway to building custom, end-to-end BNPL
  experiences directly into your platform, mobile app, or checkout flow.
  Designed with flexibility and performance in mind, our RESTf
cover: ../../.gitbook/assets/api (1).png
coverY: -38.84210526315789
layout:
  width: default
  cover:
    visible: true
    size: hero
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

# ⚙️ API GUIDE

The [PayLater ](https://paylaterapp.com/)API is your gateway to building custom, end-to-end BNPL experiences directly into your platform, mobile app, or checkout flow. Designed with flexibility and performance in mind, our RESTful APIs give you full control — from shopper onboarding and credit checks to transaction creation, refunds, and settlement reporting.

Whether you’re building a lightweight integration or a fully automated finance workflow, this section walks you through every step with clear endpoints, authentication guides, sample requests, and best practices.

### What You’ll Find Here:

OAuth 2.0 Client Credentials

* [Retrieve Your OAuth Credentials](get-access-token.md)

Process Transactions

* [Generate Payment Link](generate-payment-link.md)
* [Request to Pay (POS)](request-to-pay.md)
* [Check Order Status](check-payment-status.md)
* [Get Shopper Information](get-shopper-information.md)
* [Get Transaction by Order ID](get-transaction-by-order-id.md)
* [Get Transactions](get-transactions-list.md)
* [Refund](refund-api.md)
* [Partial Refund](partial-refund.md)
* [Webhook Intergration](webhook-integration.md)
* Error handling & response codes

Start integrating and unlock the power of [PayLater ](https://paylaterapp.com/)— where flexibility meets finance, one API call at a time.

## 🔐Authentication

All API requests must be authenticated using an `Authorization Bearer Token`. This key is issued to each merchant and must be included in all requests.\
\
To receive this Bearer Token use [Retrieve your OAuth Credentials](get-access-token.md) API.

