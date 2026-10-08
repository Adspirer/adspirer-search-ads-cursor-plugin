---
name: adspirer-search-setup
description: Connect Adspirer Search Ads and the relevant Google or Microsoft account without losing the user's original task.
---

# Connect and resume

Load adspirer-search-mcp. Remember the user's task and ask only for information needed for it.
If the connection is unavailable, guide the user through Cursor/Grok Bot's supported MCP
authentication UI. Never use Claude-specific installation commands.
Once authorized, inspect get_connections_status if advertised. Connect only the required
provider at https://www.adspirer.com/connections; do not require every integration.
For multiple accounts, ask which one to use. Do not silently activate or switch accounts.
Competitor research may not need an ad account, but does require identity and plan eligibility.
Call start_here when helpful, not as a mandatory detour. Resume the original request after
authentication and deliver one useful result. Account connection alone is not task success.
