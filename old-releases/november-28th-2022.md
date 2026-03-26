# November 28th, 2022

## Bug Fixes

Fixed an issue with Robinhood market buy orders not filling sometimes. Under the hood in Robinhood, market orders are actually limit orders with a 5% collar.

We updated our integration to apply the 5% collar so that buy market orders can have a higher chance of filling.

Previously, we would send a limit price with the current market price and if the price moves fast enough, you may not get filled. The collar gives you 5% wiggle room to get filled. You can read more about this [here](https://robinhood.com/us/en/support/articles/market-order/#Marketordercollaring).
