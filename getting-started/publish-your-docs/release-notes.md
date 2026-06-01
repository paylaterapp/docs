# Release Notes

<details>

<summary>Release Notes v3.0 (May 17, 2026)</summary>

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

<summary>Release Notes v2.0 (April 30, 2026)</summary>

* 🛠 Technical Refactor & Compatibility
  * The order lifecycle has been refactored to match the standard Magento redirect-gateway pattern
  * On the success-return URL, the module calls PayLater's web-checkout/status API and only marks the order
  * **Authorization & Capture**
* ⚙️ Reconciliation Cron
  * A new paylater\_reconcile\_pending\_orders cron runs every 10 minutes as a safety net for redirect-flow edge cases
  * For each pending\_payment PayLater order older than 3 minutes, queries web-checkout/status.

</details>

<details>

<summary>Release Notes v1.3 (January 28, 2026)</summary>

* 🎨 Design & UX Enhancements
  * Updated Branding
  * New Visibility Widgets
* 🛠 Technical Refactor & Compatibility
  * **Seamless Redirect**
  * **Order Success Sync**
  * **Authorization & Capture**
* ⚙️ 3 Admin Configuration & Workflow
  * New Admin Controls
  * Widget Management: New toggles in Stores > Configuration to enable/disable\
    widgets per page type (Global, PDP, or Listing).
  * Setup Wizard: Streamlined the onboarding steps within the Magento Admin for faster\
    merchant activation.
  * Debug Logging: Enhanced logging for API requests to assist in troubleshooting\
    transaction failures.

</details>

<details>

<summary>Release Notes v1.2 (March 28, 2025)</summary>

* 🎨 Design & UX Enhancements
  * Payment Method Logo
  * Checkout Display
* 🛠 Technical Refactor & Compatibility
  * Platform Alignment
  * Magento 2.4.7+ Support: Full compatibility verified with PHP 8.1, 8.2, and 8.3.
* ⚙️ 3 Admin Configuration & Workflow
  * Environment Toggle
  * API Management
  * Setup Wizard
  * Debug Logging

</details>
