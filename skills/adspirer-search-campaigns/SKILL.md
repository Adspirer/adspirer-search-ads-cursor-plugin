---
name: adspirer-search-campaigns
description: Plan and create user-approved paused Google Ads or Microsoft Advertising campaigns from research.
---

# Plan, approve, build paused

Load adspirer-search-mcp. Confirm provider/account, geography, language, objective, landing
page, conversion setup, budget amount/currency, and bid strategy. Read current account state.
Discover actual platform read and write operations before constructing payloads.
Present ad groups, keyword match types, negatives, copy, budgets, and measurement assumptions.
Get explicit approval for the concrete plan before any creation or update.
Set the newly created campaign to paused using the exact schema. If paused creation cannot
be established, stop before creating it. Never enable it as part of routine setup.
Read back campaign status, budget, account, and created resources; report IDs and any
partial failures. Do not blindly retry creations or claim a plan was executed.
Launching later needs separate explicit approval. Never promise conversions or profitability.

## Quality Score and impression share

On Google, read Quality Score and impression share before recommending more budget. Lost IS (budget) is a budget opportunity when the extra clicks are worth it. Lost IS (rank) is a bid, Quality Score, or relevance opportunity — raising the budget does not recover it. Label the account, campaign, and date range. Microsoft impression-share parity is not assumed; if the catalog has no such report, write "not available".

## Launch preflight

Before calling a Search build finished, confirm all of these:

- Negatives from the plan are in place at the agreed scope and match type.
- At least 4 sitelinks and 4 callouts are on the campaign (Google Search; add the Microsoft equivalents the live schema supports).
- Networks are checked: Search Partners and Display are off unless the approved plan turned them on.
- Conversion tracking for the goal is verified (adspirer-search-measurement), not assumed from a tag warning.
- The campaign was created paused, and a read-back confirms it is still paused.
