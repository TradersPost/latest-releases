---
description: >-
  This is a summary of various bug fixes and changes made to the TradersPost
  platform over the last several weeks.
---

# January 6th, 2025

* Fixed an issue where the `Disable canceling open orders` setting mistakenly affected explicit `action=cancel` webhooks. Now, you can send an explicit `action=cancel` webhook to cancel orders for a ticker, regardless of whether the setting is enabled or disabled
* Resolved an Interactive Brokers issue where orders for OTC tickers with empty quotes were not submitted correctly to the IBKR API.
* Fixed an issue with the TradersPost internal market clock where Tradier's post-market extended hours orders failed to submit after 7 PM Eastern Time.
* Fixed a bug that affected the rendering of Interactive Brokers orders submitted outside of TradersPost during the overnight trading session. Previously, these orders were not handled correctly, causing issues with the closed orders list UI.
* Disallowed `+` to be used in email addresses when registering new accounts.
* Fixed Robinhood OAuth integration and Two-Factor authentication methods that would cause users to not be able to connect their Robinhood account to TradersPost.

## Performance Improvements

We've significantly enhanced our trade queuing infrastructure, allowing trades to begin execution in approximately 100ms or less with greater consistency. Additionally, we’ve improved our integration with broker APIs by making more requests asynchronously, which reduces the time it takes to plan and execute trades, resulting in faster and more efficient trade processing.
