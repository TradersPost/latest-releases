# March 25th, 2026

### Close Positions Enhancement

Closing a position (or all open positions) now optionally cancels relevant open orders before TradersPost submits the exit orders

* Close Position: check “Cancel open {SYMBOL} orders first” to cancel open orders for that ticker, then place the exit order.
* Close All Positions: check “Cancel all open orders first” to cancel open orders, then place exit orders for all open positions.

Canceling orders cannot be undone—you’ll need to recreate any orders if needed.

<figure><img src=".gitbook/assets/Screenshot 2026-03-25 at 4.54.19 PM.png" alt=""><figcaption></figcaption></figure>

### Bug Fixes

* The signal quantity multiplier functionality was incorrectly applying when `quantityType` has a value of `percent_of_position`.
