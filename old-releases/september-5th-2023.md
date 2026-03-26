# September 5th, 2023

On Sunday, September 3rd at around 10:30am a bug was inadvertently introduced to the TradeStation integration that was causing order history to not show Futures or Options orders when you have the Stocks asset class disabled under My Account > Asset Classes within TradersPost.&#x20;

This was causing trade execution to not be able to see Futures or Options open orders orders to be able to cancel them before sending new orders.

This only affected accounts with the Stocks asset class disabled under My Account > Asset Classes within TradersPost.

This issue was identified on Monday, September 5th 9:42am CDT was resolved at 12:28PM CDT.

We apologize for the problem and inconvenience this may have caused. We take the stability of the TradersPost system seriously and we've expanded our automated test suite to cover these scenarios more thoroughly so that it does not occur again.
