---
icon: shopify
cover: https://cdnmp.plentymarkets.com/20837/meta/images/preview_0.png
coverY: 60.490789473684224
coverHeight: 269
layout:
  width: default
  cover:
    visible: true
    size: hero
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Shopify

The PayLater plugin offers merchants the ability to integrate "Buy Now, Pay Later" (BNPL) functionality into their Shopify stores, providing customers with flexible payment options. This comprehensive guide will walk you through the step-by-step installation and configuration process for seamless integration.

## Manual Step

### Step 1: Setup PayLater as a Manual Payment Method

* Go to your Shopify Admin (ex. \[yourstore.com].myshopify.com/admin) and click on Settings in the left-hand navigation panel

<figure><img src="../.gitbook/assets/1 (3).png" alt=""><figcaption></figcaption></figure>

* Click on the “Payment Menu” from left menu & scroll down to the “Manual payment methods” section.

<figure><img src="../.gitbook/assets/2 (4).png" alt=""><figcaption></figcaption></figure>

* In this section, click on the dropdown labeled “Manual payment methods” and select "Create custom payment method"

<figure><img src="../.gitbook/assets/3 (3).png" alt=""><figcaption></figcaption></figure>

* In the “Set up manual payment form”, copy/paste the details as shown below in the appropriate field (NOTE: You can write according to your checkout design):
  * (Custom payment method name) Split in 4 interest-free payments with PayLater<br>
  * (Additional Details) PayLater allows you to split your purchase into  4  interest-free installments.
  * (Payment Instructions) You'll receive an email with a secure link from PayLater to complete your payment.

<figure><img src="../.gitbook/assets/4 (3).png" alt=""><figcaption></figcaption></figure>

* Click on the "Activate" button to save your work. You will see “Split in 4 interest-free payments with PayLater“ appear under the Manual Payment Methods.

<figure><img src="../.gitbook/assets/5 (3).png" alt=""><figcaption></figcaption></figure>



### Step 2: Create the PayLater Private App

* In Settings, go to “Apps and sales channel“ in the left menu and then click on the Develop apps button on the top.

<figure><img src="../.gitbook/assets/6 (3).png" alt=""><figcaption></figcaption></figure>

* Click on “Allow legacy custom app development“.

<figure><img src="../.gitbook/assets/7 (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/8 (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/9 (3).png" alt=""><figcaption></figcaption></figure>

* In the “Create an app” form, Set “PayLater Payment” as App name.

<figure><img src="../.gitbook/assets/10 (3).png" alt=""><figcaption></figcaption></figure>

* You will be redirected to the below screen. Navigate to “Configuration”.

<figure><img src="../.gitbook/assets/11 (3).png" alt=""><figcaption></figcaption></figure>

* Under “Configuration”, click on “Configure” button next to “Admin API integration” to add scope permissions.

<figure><img src="../.gitbook/assets/12 (3).png" alt=""><figcaption></figcaption></figure>

* Scroll down and modify the following access in each respective dropdown. You do not need to modify any other dropdowns.
  * Orders (Read and Write)
  * Fulfillment Services (Read and Write)

<figure><img src="../.gitbook/assets/13 (3).png" alt=""><figcaption></figcaption></figure>

* Click "Save" button. This will add scope configuration for admin

<figure><img src="../.gitbook/assets/14 (3).png" alt=""><figcaption></figcaption></figure>

* Now go to “API Credentials” section in the “Apps and sales channel” navigation and click on “Install app” button. It will prompt for confirmation

<figure><img src="../.gitbook/assets/15 (3).png" alt=""><figcaption></figcaption></figure>

* To protect your data, you’ll only be able to reveal your Admin API token once. Copy and save your Admin API access token in a secure place

<figure><img src="../.gitbook/assets/16 (3).png" alt=""><figcaption></figcaption></figure>

* Copy the API Key and  Api secret key and save



### Step 3: Setting Webhook

* In Settings, go to “Notifications“ in the left menu and then click on the Webhooks.

<figure><img src="../.gitbook/assets/17 (4).png" alt=""><figcaption></figcaption></figure>

* Now click “Create webhook”

<figure><img src="../.gitbook/assets/18 (3).png" alt=""><figcaption></figcaption></figure>

* In the “Add webhook” form, copy/paste the details as shown below in the appropriate field and click on Save
  * Event (Order Creation)
  * Format (JSON)
  * URL ([https://shopify.paylaterapp.com/api/webhooks/shopify](https://shopify.paylaterapp.com/api/webhooks/shopify))
  * Webhook API version (Unstable)

<figure><img src="../.gitbook/assets/19 (3).png" alt=""><figcaption></figcaption></figure>



### Step 4 : Linking Shopify to PayLater Backend App

* In Settings, go to “Apps and sales channels“ in the left menu and then click on the “Build apps in Dev Dashboard”

<figure><img src="../.gitbook/assets/20 (3).png" alt=""><figcaption></figcaption></figure>

* Click on “Create an app“

<figure><img src="../.gitbook/assets/21 (3).png" alt=""><figcaption></figcaption></figure>

* Set “PayLater Payment” as App name

<figure><img src="../.gitbook/assets/22 (3).png" alt=""><figcaption></figcaption></figure>

* Fill App URL form with [https://shopify.paylaterapp.com/api/webhooks/shopify](https://shopify.paylaterapp.com/api/webhooks/shopify) value

<figure><img src="../.gitbook/assets/23 (3).png" alt=""><figcaption></figcaption></figure>

* Select below mentioned Scopes
  * Orders (Read and Write)
  * Fulfillment Services (Read and Write)

<figure><img src="../.gitbook/assets/24 (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/25 (3).png" alt=""><figcaption></figcaption></figure>

* Also set Redirect URLs form with [https://shopify.paylaterapp.com/api/webhooks/shopify](https://shopify.paylaterapp.com/api/webhooks/shopify) value

<figure><img src="../.gitbook/assets/26 (3).png" alt=""><figcaption></figcaption></figure>

* Click “Release”

<figure><img src="../.gitbook/assets/27 (3).png" alt=""><figcaption></figcaption></figure>

* Set Version name (optional) and then click “Release”
  * Version name (optional) ⇒ v1-2025

<figure><img src="../.gitbook/assets/28 (3).png" alt=""><figcaption></figcaption></figure>

### Final Step:

* Save all the keys you receive during this all process.
*   Send following keys to your account manager to activate your store for payments.

    * Shop Url (store.com)
    * Access Token (shpat\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*)
    * Shopify API Secret (shpss\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*)



