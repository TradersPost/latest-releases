# March 9th, 2024

## Order Queueing

We made a change to order queueing to only allow one queued trade per strategy subscription and ticker combination. This means if you send multiple trades to TradersPost when the market is closed resulting in queued trades, the previous older queued trades will be replaced with the newer trades. Only the last queued trade will be sent to the broker at the next market open.

