# Release Notes



<details>

<summary>Release Notes V2.0 (May 17, 2026)</summary>

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

<summary>Release Notes V1.0 (April 24, 2026)</summary>

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
