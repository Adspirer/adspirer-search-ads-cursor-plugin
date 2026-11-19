# Changelog

## 1.1.0

- Reports (performance review and optimize): on Grok Bot, deliver a report as a Page and update the same Page on reruns; elsewhere, one HTML or Markdown file. Label every number with platform, account, date range, timezone, and currency. Missing data is "not available", never 0. Do not sum Google and Microsoft conversions as deduplicated, or sum across currencies.
- Search terms and negatives (optimize): classify converting, unproven (below a spend floor), irrelevant, or brand-routing. Exact or phrase match; campaign, ad group, or shared-list scope. A negative must not block a converting keyword or duplicate an existing one. A brand term in a non-brand campaign is a routing negative. Propose every change in one table and apply only after explicit approval.
- Measurement: always pass the account id to `audit_conversion_tracking`, retry once, then fall back to read-only conversion-action reads. "Not connected" is a connection gap, not a tracking failure. Judge each action by its source. Flag "XXX" currency and duplicate primary actions. Conflicting reads are verified in the ads UI.
- Google Ads and campaigns: Quality Score and impression share, with lost IS (budget) versus lost IS (rank) as the opportunity. Launch preflight: negatives in place, at least 4 sitelinks and 4 callouts, Search Partners and Display off unless intended, conversion tracking verified, created paused.
- Creative: Google RSA limits (15 headlines ≤30 characters, 4 descriptions ≤90, path fields ≤15), the pinning trade-off, and one test at a time.
- Pacing (optimize): threshold defaults, a quiet floor for tiny accounts, wait for the platform data upload delay before alerting, and Google can spend up to 2× its daily budget on a day.
- New reference `skills/adspirer-search-agent/references/ui-checks.md` (not a skill): read-only Google Ads and Microsoft Advertising UI checks when the host has a browser. Sign-in is the user or a password manager; never passwords or codes in chat. Linked from adspirer-search-agent.
- Repeating work: on Grok Bot, scheduled routines ship off and skip runs while the connector is signed out.
- Microsoft: a scheduled Google import can overwrite Microsoft-side edits.
- Still 16 skills. This repository does not auto-sync from amekala/ads-mcp.

## 1.0.4

- Lead the marketplace description with the advertising specialty for clearer truncated previews.

## 1.0.3

- Restored adapted docs, agent, creative, and performance-review skill families.
- Expanded setup and optimization to preserve transferable original workflow guidance.
- Added an explicit original-to-specialist skill map; total 16 skills.

## 1.0.2

- Shortened marketplace summary; retained detailed positioning in README.
- Corrected negative-keyword wording and removed the out-of-box autonomous-operation claim.
- Scoped performance-reporting copy to Google Ads.
- Updated PMax reporting references and replaced fixed bidding thresholds with a conditional decision framework.
- Preserved Research category, black logo, MCP endpoint, and approval safeguards.

## 1.0.1

- Updated manifest and README with the publisher-provided PPC and paid-search positioning.
- Clarified approval, paused creation, host automation requirements, and platform-specific reporting scope.

## 1.0.0

- Initial standalone Search Ads Cursor/Grok Bot distribution.
- Twelve focused skills, one subagent, one task-scoped rule, and the existing Search Ads MCP endpoint.
- Reused and adapted the main plugin's Google Ads skill and four references; added Microsoft Ads, GA4, GSC, and GTM guidance.
- Research category requested; no marketplace approval claimed.
