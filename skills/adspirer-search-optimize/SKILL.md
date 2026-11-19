---
name: adspirer-search-optimize
description: Analyze Google paid-search waste and budget pacing, inspect Microsoft campaigns, and apply only explicitly approved changes.
---

# Cutting waste and pacing budgets

Adapted from adspirer-optimize. Load adspirer-search-mcp and the relevant platform skill.
Propose changes, then execute only after approval of the specific action and account.

## Find waste

Discover Google analyze_wasted_spend and analyze_search_terms through google_ads_read. For Microsoft, inspect available campaign configuration; do not invent equivalent reporting tools.
Distinguish zero conversions, high CPA, irrelevant traffic, placement/audience mismatch,
tracking gaps, and weak creative. Do not label small samples or conversion lag as failure.

## Search terms and negatives

Classify each term before proposing a negative:

- **Converting** — has conversions in the window. Do not block it.
- **Unproven** — spend is below a spend floor (default: about 3× target CPA, or about 50 in account currency when there is no target). Lack of conversions here is not failure.
- **Irrelevant** — off-intent (jobs, free, the wrong product or language) with enough spend or an obvious mismatch.
- **Brand-routing** — a brand term in a non-brand campaign is a routing negative, not wasted spend. It belongs on the non-brand campaign so brand traffic stays in the brand campaign.

Use exact match for one query and phrase match when that word sequence is unwanted. Do not use a broad negative unless the user wants every query containing those words blocked.
Scope: ad group when only that group is wrong; campaign when the campaign should not match it; a shared list when the same negative applies across campaigns. Confirm the live schema — campaign negatives and shared lists are not ad-group writes.
Read existing negatives first. Drop the proposal if it duplicates one already at that scope or on an attached list, or if it would block a converting keyword.
Propose every change in one table: platform, account, scope, match type, term, reason, and evidence. Apply only after explicit approval of that table.

## Before cutting

Check audit_conversion_tracking where supported. Broken tracking limits conversion-based
decisions; missing events do not prove no business results occurred.
Assess sample size, spend relative to the goal, attribution, and upper-funnel contribution.
Avoid universal click counts, CPA multiples, or frequency cutoffs as automatic pause rules.

## Propose the smallest effective change

For irrelevant search terms, propose negatives with exact scope and match type before broad pauses.
Consider exclusions or creative tests, then pausing the narrowest resource needed.
Prefer reversible actions. Deletion/removal requires explicit authorization and explanation
of what is actually irreversible; do not assume all historical reporting disappears.
Do not automatically apply the output of a tool whose name says optimize.

## Budget allocation and pacing

Compare period spend with elapsed time, remaining budget, and campaign constraints.
Show proposed before/after amounts, daily/monthly implications, account currency, and total.
Identify what constrains delivery before recommending more budget.
Avoid fixed percentage increases or promises that reallocations will yield a set number of leads.
Label forecasts as conditional estimates. Discover budget-tool schemas and check whether
an operation recommends or mutates before calling it.

Thresholds below are alert defaults when the workspace has not set its own. They are not automatic pauses.
Month-to-date spend over 110% or under 80% of expected pace (budget × elapsed days ÷ days in the period). CPA over 130% of target, or ROAS under 70% of target, across the last 7 days — say where the target came from.
Quiet floor for tiny accounts: do not fire under about 100 clicks, under 5 conversions for a CPA or ROAS rule, or under 50 in account currency for the window.
Wait for the platform's data upload delay before alerting. Yesterday's clicks often arrive hours later, and conversions lag longer. Do not treat an incomplete day as a zero.
Google can spend up to 2× its daily budget on a day and settle over the month. A single day inside that range is not an overspend alert.

## How to deliver the report

On Grok Bot, deliver reports as a Page and update the same Page on reruns; elsewhere, one HTML or Markdown file.
Label every number with platform, account, date range, timezone, and currency.
Write missing data as "not available" (never 0).
Never sum Google and Microsoft conversions as if they were deduplicated, and never sum amounts across currencies.

## Verify and repeat

After approved changes, read back affected resources and report partial failures honestly.
Inspect state before retrying uncertain writes. Do not enable paused campaigns implicitly.
Offer a host schedule only if supported and authorized; disclose quota implications.
The specialist endpoint does not expose the main monitoring_and_reporting router.
Do not claim continuous monitoring unless an actual configured scheduler confirms it.
