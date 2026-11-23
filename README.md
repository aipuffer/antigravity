# AI Puffer for Google Antigravity

Manage your WordPress website through natural-language requests: read content, create drafts, update WooCommerce products, improve SEO and work with supported page builders.

## Connect your website

1. Install and activate [AI Puffer](https://wordpress.org/plugins/gpt3-ai-content-generator/) on your WordPress website.
2. In WordPress, open **AI Puffer → Settings → Connections → Manage my website**. Complete Cloud account setup if requested.
3. Under **Add an assistant**, review the WordPress user and safety level. Select **Set it up manually** and complete any displayed connection step in your browser.
4. Install this package in Antigravity, then authenticate its AI Puffer MCP server. Finish authorization in the same browser used for WordPress, within ten minutes of starting setup.
5. Check the website, acting user and access level shown on the consent screen before allowing access.

If authorization asks you to start from WordPress, repeat the WordPress setup step, then retry authentication. No API key or WordPress password belongs in the package configuration.

## Install from GitHub

With Git and Google’s Antigravity CLI installed, run:

```sh
git clone https://github.com/aipuffer/antigravity.git ai-puffer
agy plugin validate --strict ./ai-puffer
agy plugin install ./ai-puffer
```

This repository contains the connector package for Marketplace review. A public repository is not an approved Marketplace listing.

Open `/plugin` in Antigravity, expand **ai-puffer** under Installed, and choose **Sign in** after starting setup in WordPress. Complete the browser authorization and paste its code back into Antigravity.

## First requests

- “Show me an overview of my WordPress website. Do not change anything.”
- “Draft a welcome post for my website without publishing it.”
- “Find five products whose descriptions could be improved.”

Available operations depend on your installed plugins, edition, WordPress permissions and chosen access level. Read only access cannot make changes; Standard may require approval. Paid-only WordPress features still require their normal license.

Successful website operations use your Website actions allowance. Website actions and AI credits are separate balances. See [plans and usage](https://aipower.org/docs/reference/plans-and-usage/) for current details.

## Privacy and control

AI Puffer connects Antigravity to your selected WordPress site through its hosted MCP service. Tool results may include website content requested by the assistant. Review access in WordPress and revoke the connection when it is no longer needed. Do not retry an uncertain write blindly: the assistant should inspect the original operation and verify the result first.

The package contains only connector metadata and a logo. The hosted service provides the tools and current workflow guidance; this package does not run shell hooks, background jobs or local models.

[Manual](https://aipower.org/docs/) · [Support](mailto:support@aipower.org)

## Validation and reviewer checks

- **13 November 2026 — native end-to-end tests:** official Antigravity CLI 1.5.8, a local Bridge and a disposable WordPress site running AI Puffer 2.5.28. OAuth sign-in, tool discovery, content reads, draft creation and editing, missing-content recovery, a Read only downgrade, and revocation passed. A fresh CLI process reused the saved connection.
- **23 November 2026 — review refresh:** strict package validation passed with the official CLI 1.5.8. All 48 targeted Bridge OAuth, MCP access and catalog regression tests passed, including Google's client metadata, PKCE, optional persistent access, refresh-token rotation and authorization-code replay rejection. The live service's OAuth discovery endpoints were checked separately.

The native tests used local fixtures for Cloud identity and billing. They do not certify production billing or the separate Antigravity IDE/App interfaces. The November 23 automated checks do not represent a new native end-to-end run.

For a review on a disposable WordPress website:

1. Follow the connection steps above and choose the least access needed. Read only is enough for the first request.
2. Ask “Show me an overview of my WordPress website. Do not change anything.”
3. To test writes, choose Trusted access on that disposable website and ask for a welcome draft without publishing it. Ask for an edit to that same draft, and verify its draft status in WordPress.
4. Change the connection to Read only in WordPress and confirm that a new change is refused.
5. Revoke the connection in WordPress and confirm Antigravity can no longer access that website.

Contact [support@aipower.org](mailto:support@aipower.org) for review assistance. Never include WordPress credentials or access tokens in GitHub issues.
