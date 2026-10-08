# Reviewer checklist

## Requested listing

- Publisher: Adspirer (reuse the existing company publisher).
- Display name: Adspirer Search Ads.
- Plugin ID: adspirer-search-ads.
- Requested category: Research.
- Proposed URL shape: /marketplace/adspirer/adspirer-search-ads. Cursor assigns the actual route.
- Verification badge: requested separately; not inherited from the main listing.

## Source and limits

Derived from Adspirer/adspirer-cursor-plugin format at 4fbb827.
Search tool contract inspected in Adspirer/adstudio origin/production-deployment,
adspirer-mcp-search-ads/server.py. Deployed authenticated tools must still be reconciled.
Do not copy the main hub's google_ads router, search_tools, or hardcoded quota tables.

## Before marketplace submission

- [ ] Confirm company publisher ownership; do not create an accidental personal namespace.
- [ ] Confirm whether Cursor wants this new repo through the existing publisher/re-index process.
- [ ] Confirm underlying Adspirer subscription treatment under publisher terms section 3.1.
- [ ] Confirm Research placement and request verification.
- [ ] Install the exact commit in Cursor; test fresh and returning OAuth.
- [ ] Repeat supported installation and OAuth checks in Grok Bot.
- [ ] Verify tools/list and read-only get_connections_status against the authenticated endpoint.
- [ ] Test keyword research, competitor research, performance review, and measurement with authorized accounts.
- [ ] Test missing account, expired authentication, unavailable operation, and quota errors.
- [ ] Co-install the main plugin; confirm routing does not duplicate actions or use the wrong server.
- [ ] With explicit user approval, create one paused campaign and verify it remains paused.
- [ ] Confirm hosted documentation, policy, and support links before submission.
- [ ] Capture a reviewer-accessible demo if requested; never place reviewer credentials here.

Repository publication, marketplace submission, approval, installation, authorization,
and successful tool use are separate milestones.
