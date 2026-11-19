---
name: adspirer-search-measurement
description: Audit search-ad conversion tracking and investigate performance using available Google Analytics, Search Console, and Tag Manager tools.
---

# Measurement and conversion tracking

Load adspirer-search-mcp. Identify the conversion event, account/property/container, time
range, attribution basis, and business objective. Ask for additional connections only when
the current question needs them.
Discover audit_conversion_tracking and available GA4, GSC, and GTM tools and schemas.
Start with reads. Separate Google Ads conversions, GA4 events, and Search Console organic
clicks; they have different definitions and should not be treated as interchangeable.

## Conversion audit

Always pass the account id to `audit_conversion_tracking`. If it still asks which account, or ignores the id, retry once, then fall back to read-only conversion-action reads on the Google read router.
"Not connected" is a connection gap, not a tracking failure. Send the user to connect the account; do not grade the tag.
Judge each conversion action by its source: website tag, GA4 import, offline or API upload, calls, or a lead form. A tag warning does not condemn an import.
Flag a placeholder currency "XXX" and duplicate primary actions that count the same event twice (for example a tag and a GA4 import both primary on one purchase).
When two reads conflict, verify them in the ads UI before recommending a fix. Use the read-only checks linked from adspirer-search-agent. Primary versus secondary is set in the ads UI.
The Google audit does not cover Microsoft. UET tags, goals, and a Google import are a UI check, not a failed Google audit.
Report verified findings, unknowns, access gaps, and prioritized fixes. An absent event in
a sample does not establish broken tracking. Do not promise complete multi-touch attribution.
Publishing a GTM container, editing tags, changing conversion actions, or other writes needs
specific approval and a rollback plan. Verify after approved changes; do not report success
solely because a write request was accepted.
