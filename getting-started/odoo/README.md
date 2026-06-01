---
icon: '0'
cover: ../../.gitbook/assets/Official_Odoo_logo.svg.png
coverY: 0
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

# Odoo

Empower your Odoo online store with the PayLater Odoo Plugin, a cutting-edge solution designed to enhance the purchasing journey for both merchants and customers. This seamlessly integrated plugin opens up a world of possibilities, allowing merchants to offer a convenient and flexible PayLater option at checkout.

## Download Plugin

#### Version 2.0

**Release Notes:** Webhook, Partail Refund, Full Refund, [Click Here](release-notes.md#release-notes-v2.0-may-17-2026)

**Plugin:**&#x20;

{% file src="../../.gitbook/assets/payment_paylater-v2.0.zip" %}

#### Version 1.0

**Release Notes:** Initial Launch, Core Payment Gateway Integration, [Click Here](release-notes.md#release-notes-v1.0-april-24-2026)

**Plugin:**&#x20;

{% file src="../../.gitbook/assets/payment_paylater-v1.0.zip" %}

## Installation

Paylater empowers merchants to offer the popular Buy Now, Pay Later (BNPL) payment option to their customers on their Odoo websites. This document guides you through the installation and setup process of the&#x20;PayLater&#x20;plugin.

### Before you begin:&#xD;

Ensure you have a&#x20;Odoo Website&#x20;with the&#x20;Odoo plugin&#x20;installed and activated.

### Frontend Widgets:

PLP Product List Page

<figure><img src="../../.gitbook/assets/Screenshot from 2026-02-02 17-01-18.png" alt=""><figcaption></figcaption></figure>

PDP Product Detail Page

<figure><img src="../../.gitbook/assets/Screenshot from 2026-02-02 17-01-45.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot from 2026-02-02 17-08-29.png" alt=""><figcaption></figcaption></figure>

Checkout Page

<figure><img src="../../.gitbook/assets/odoo-app-checkout.png" alt=""><figcaption></figcaption></figure>

## Method: Manual Installation

The manual installation method involves downloading our plugin and uploading it to your web server via your favorite FTP application. The Odoo codex contains&#x20;[Manage Plugins](https://wordpress.org/documentation/article/manage-plugins/#Manual_Plugin_Installation)

<figure><img src="../../.gitbook/assets/oddo-app.png" alt=""><figcaption><p>After Uploading via FTP, you can see PayLater Payment Gateway in Plugin List</p></figcaption></figure>

## Configurations

* Once activated, navigate to  &#x20;**Odoo -> Apps -> Payments**
* Locate  &#x20;PayLater  &#x20;in the list of available payment gateways and click on the  &#x20;Manage  &#x20;button.

<figure><img src="../../.gitbook/assets/odoo-app-install.png" alt=""><figcaption></figcaption></figure>

* Then, navigate to  &#x20;**Odoo -> Webstite -> Configuration -> Payment Provider**

<figure><img src="../../.gitbook/assets/odoo-app-config.png" alt=""><figcaption></figcaption></figure>

* Enter your  &#x20;Merchant ID  &#x20;and  &#x20;Outlet ID  &#x20;provided [here](../../#test-credentials). These credentials are crucial for secure communication between your store and the PayLater platform.

<figure><img src="../../.gitbook/assets/odoo-app-config-1.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/odoo-app-config-2.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/odoo-app-config-3.png" alt=""><figcaption></figcaption></figure>

* For Widget settings, navigate to  &#x20;**Setting -> Paylater**

<figure><img src="../../.gitbook/assets/odoo-app-setting.png" alt=""><figcaption></figcaption></figure>

* Click  &#x20;Save Changes  &#x20;to complete the configuration&#x20;

## Testing

To ensure smooth functionality, it's recommended to test the PayLater payment option:

* Add a product to your cart and proceed to checkout
* During checkout, select  &#x20;PayLater  &#x20;as the payment method.
* You will be redirected to the secure PayLater platform to complete the BNPL payment process.
* Use test shopper account provided in Testing Credentials
* Please use 300 QAR as the amount to test























