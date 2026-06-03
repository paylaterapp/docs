# Release Notes



<details>

<summary>Release Notes V4.0 (June 04, 2026)</summary>

* ✨ OAuth2 Bearer authentication
  * Authentication switched from x-api-key to OAuth2 Bearer
  * Endpoints moved to /v2/web-checkout.
  * Payload field names are snake\_case. outletId → outlet\_id, orderId → order\_id, successRedirectUrl → success\_redirect\_url, failRedirectUrl → fail\_redirect\_url.
  * expiry\_duration is now required on create-payment-link.
  * Full and partial refunds collapse onto one endpoint.
* 🔐 Admin validation
  * Admin settings rearranged. The Test API Key and Live API Key fields are removed.
  * New fields added: Test Client ID, Test Client Secret, Live Client ID, Live Client Secret.

</details>

<details>

<summary>Release Notes V3.0 (May 17, 2026)</summary>

* ✨ New features
  * Online refunds from orders admin screen — calls PayLater's gateway directly, no manual reversal needed
  * Full refund routing: GET /web-checkout/refund with transactionType=DOWN\_PAYMENT when credit memo amount equals order total
  * Partial refund routing: POST /web-checkout/refund/partial with {"amount":...} when amount is less than total
  * Webhook receiver at POST for server-to-server settlement
  * Webhook Secret admin field (encrypted) for signature verification
* 🔐 Admin validation
  * Minimum Order Amount must be ≥ 300 at save time
  * Validation (validate-number validate-greater-than-zero) on the minimum amount field for immediate feedback
  * API Key validation preserves placeholder behaviour — admin doesn't have to re-paste the key on every save

</details>

<details>

<summary>Release Notes V2.1 (April 30, 2026)</summary>

* 🛠️ Architectural Improvements
  * Callback orderId is now bound to the order's stored reference.
  * Order is rejected if it was not initiated through PayLater.
  * All redirects switched to wp\_safe\_redirect() to prevent off-host redirection.
  * Error field parsing aligned with the gateway contract.

</details>

<details>

<summary>Release Notes V2.0 (January 28, 2026)</summary>

* 🌟 New "PayLater" Features
  * Dynamic Monthly Installments
  * Collapsible PDP Widget
  * PLP Summary Bar
* 🛠️ Architectural Improvements
  * Bulletproof Admin Interface
  * WooCommerce Blocks Integration
  * HPOS (High-Performance Order Storage) Certified
  * Unified Asset Management
* 🎨 Visual & UI Enhancements
  * Full-Width Branding
  * Branded Loader Overlay
  * Mobile Optimized:

</details>

<details>

<summary>Release Notes V1.0 (June 28, 2025)</summary>

* 🌟 Core Payment Features
  * Direct API Handshake
  * Order Total Logic
  * Classic Checkout Support
* 🛠️ Architectural Improvements
  * Centralized Admin Dashboard
  * Dual Environment Support
  * Secure API Handling
  * Automated Refund Engine
* 🎨 Checkout UI & Security
  * Security Callback Handler
  * Smart Redirects
  * Mobile Optimized

</details>

