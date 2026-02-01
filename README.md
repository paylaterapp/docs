---
icon: hand-wave
cover: .gitbook/assets/1_PAYLATER_BANNER_1710X525_HOME.png
coverY: 0
---

# Get Started

Welcome to the [PayLater](https://paylaterapp.com/) Integration Documentation — your gateway to embedding seamless Buy Now, Pay Later (BNPL) experiences into your online store or application.

[PayLater](https://paylaterapp.com/) allows merchants to offer flexible, interest-free installment plans at checkout, helping boost conversions, average order value, and customer satisfaction. Whether you're running a custom-built website or using a popular eCommerce platform, our integration options are built for speed, reliability, and scalability.

## 💡 Integration Options

You can integrate [PayLater ](https://paylaterapp.com/)using one of the following methods:

* **API Integration** – Ideal for custom platforms, mobile apps, and businesses seeking full control over the user experience.&#x20;
  * **Mobile App Integration:** For integrating to your your native mobile application, you may need to active camera access option "onRequestPermission Callback" to process the transaction.&#x20;
* **Magento Plugin** – Easily enable [PayLater](https://paylaterapp.com/) on your Magento store with minimal configuration.
* **WooCommerce Plugin** – Connect [PayLater ](https://paylaterapp.com/)to your WordPress-based WooCommerce site in just a few clicks.
* **Shopify** – Activate [PayLater ](https://paylaterapp.com/)for Shopify to implement PayLater as a payment option

This documentation covers everything you need — from authentication and transaction flows to refund handling and settlement reports. Whether you're a seasoned developer or just starting out, we’ve got you covered.

Let’s dive in and get you up and running in no time.

## Test Credentials

**MerchantID:** 138\
**API Key:** a4f9feba-19dd-47b7-8d09-268a25c44a35\
**OutLet ID:** 1000000061

## Test Shopper Accounts

Please use the below test accounts. The OTP you can use is 1234

<table><thead><tr><th width="271.4296875">Phone Number</th><th>OTP</th><th>Email</th></tr></thead><tbody><tr><td>51118021 </td><td>1234</td><td>qid8021@mailinator.com</td></tr><tr><td>51118022</td><td>1234</td><td>qid8022@mailinator.com</td></tr><tr><td>51118023</td><td>1234</td><td>qid8023@mailinator.com</td></tr><tr><td>51118024</td><td>1234</td><td>qid8024@mailinator.com</td></tr><tr><td>51118025</td><td>1234</td><td>qid8025@mailinator.com</td></tr></tbody></table>

### Successful Cases Test Cards <a href="#successful-cases-test-cards" id="successful-cases-test-cards"></a>

| **Card Type**        | **Card Number**     | **Expiry Date** | **CVV** |
| -------------------- | ------------------- | --------------- | ------- |
| MasterCard           | 5200 0000 0000 2151 | 10/2028         | 237     |
| Visa                 | 4000 0000 0000 2503 | 10/2028         | 442     |
| MasterCard (Non-3DS) | 5200 0000 0000 0007 | 04/26           | 256     |

### Failed Cases Test Cards <a href="#failed-cases-test-cards" id="failed-cases-test-cards"></a>

| Card Type  | Card Number         | Expiry Date | CVV |
| ---------- | ------------------- | ----------- | --- |
| MasterCard | 5200 0000 0000 2490 | 04/2028     | 256 |
| Visa       | 4000 0000 0000 2370 | 06/2028     | 256 |

### Test Debit Card (NAPS) <a href="#test-debit-card-naps" id="test-debit-card-naps"></a>

| Card Number         | Expiry  | OTP    | CVV |
| ------------------- | ------- | ------ | --- |
| 4215 3755 0088 3243 | 06/2026 | 123456 | 123 |



## Jump right in

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>API Integration</strong></td><td>Full control. Flexible integration. Built for scale.</td><td></td><td><a href="getting-started/quickstart/">quickstart</a></td><td><a href=".gitbook/assets/api.png">api.png</a></td></tr><tr><td><strong>Magento</strong></td><td>Enable PayLater at checkout in minutes</td><td></td><td><a href="/broken/pages/7aUFmnCMx9m4smGncsXL">Broken link</a></td><td><a href=".gitbook/assets/magento.png">magento.png</a></td></tr><tr><td><strong>WooCommerce</strong></td><td>Install. Activate. Offer PayLater — it’s that easy.</td><td></td><td><a href="getting-started/publish-your-docs/">publish-your-docs</a></td><td><a href=".gitbook/assets/woocomerce.png">woocomerce.png</a></td></tr><tr><td>Shopify</td><td>Activate PayLater on your shopify checkout.</td><td></td><td><a href="getting-started/shopify.md">shopify.md</a></td><td><a href=".gitbook/assets/preview_0.png">preview_0.png</a></td></tr></tbody></table>
