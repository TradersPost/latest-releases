# February 5, 2022

## Feature Enhancements

This release contains a variety of different improvements to the system across options, futures and other functionality.

### Futures

* Add support for futures paper trading with the TradeStation broker. Initially supported tickers are NQ, MNQ, ES and MES.
* Enhance TradersPost paper trading system to support futures trading.

### Options

* Improve stock options option chain user interface and improve performance of loading option chain data from brokers.
* Enhance TradersPost paper trading system to support stock options trading.
* Add `Both` feature to the `Option Type` dropdown in options strategies. This feature allows you to buy calls when receiving a bullish signal and buy puts when receiving a bearish signal.
* Always queue stock options trades for the next market open that are triggered via signals received when the stock options market is closed.
* Fix issue with exiting long puts in stock options functionality when `Sides` is set to `Bearish`.

### Other

* Allow `Both` sides option in strategy subscriptions to be checked for live accounts. This feature was in beta and only available on paper accounts but it is broadly available for live accounts now.
* Rename `Long` and `Short` to `Bullish` and `Bearish` in the Sides dropdown so it makes more sense in the context of options where you may be bearish and want to buy long puts instead of selling short calls.
* Allow TradersPost paper accounts to use live data from a connected broker.
* Add ability for users to enable and disable stocks, options and futures trading functionality without having to contact TradersPost support.
* Add `Limit to TrendSpider` checkbox in webhooks to compliment the `Limit to TradingView` checkbox.
* Allow hardcoded quantity to be configured in a strategy instead of dynamically calculating a quantity. This is useful for stock options and futures trading where a user may just want to always trade 1 or 2 contracts consistently.
* Allow TradeStation connections to be "cloned" so that you can connect multiple different TradeStation accounts to TradersPost. This is necessary to that you can share an access token between a margin account and a futures account for example.
* Add ability to View Quote from a ticker page to view quote data for a ticker from your connected broker.
* Enhance Debug data so that it is hidden by default and made available by clicking the `Debug` button at the bottom of the page.
* Make it easier for Webhook URLs to be copied and make the URL more visible at the top of the webhook pages.
* Allow Webhook Logs and Strategy Subscription Trades to be searched by ticker name.
* Add ability to view an individual order on a specific page by clicking the View Order button or by clicking the Order ID in the expanded order row details.
* Improve ticker search bar user interface to make it a little more visually appealing.
* Add ability to preview both a bullish and bearish example when a strategy subscription has Both Sides selected.

## Bug Fixes

* Don't allow `Allow entry extended hours` or `Allow exit extended hours` checkboxes to be checked in options strategies.
* Fix issue with TradersPost paper accounts failing to execute orders in some scenarios when many orders are executing concurrently on one account.
* Don't allow TradersPost paper accounts to be Reconnected. Clicking Reconnect on a TradersPost paper broker would cause the paper account balances to be corrupted.
