# August 4th, 2024

## Fix Kraken Error

Fix error that occurred when using `BTC-USD` as the symbol for Kraken instead of `XBT-USD`. This error made it impossible for the end user to see that `BTC-USD` is not a valid symbol for Kraken.

## Fix Bybit Reconnect Button

Fix so that the "Reconnect" button shows whenever Bybit access token expires and API calls to Bybit fail with access token expired response.
