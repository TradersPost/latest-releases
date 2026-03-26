# December 5th, 2022

## Improvements

We added support for trailing stops in the TradeStation broker integration. You can now submit a trailing stop that is percentage or dollar based.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-05 at 4.18.58 PM.png" alt=""><figcaption><p>Order confirm model</p></figcaption></figure>

In your strategy subscription settings you can now also configure a trailing stop loss for subscriptions connected to TradeStation.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-05 at 4.18.23 PM.png" alt=""><figcaption><p>Strategy subscription Stop Loss settings</p></figcaption></figure>

Or you can send your trailing stop along with your entry signal.

```json
{
    "ticker": "TSLA",
    "action": "buy",
    "price": "182.45",
    "stopLoss": {
        "type": "trailing_stop",
        "trailPercent": 1
    }
}
```

Or if you want to specify a trail price you can do that as well.

```json
{
    "ticker": "TSLA",
    "action": "buy",
    "price": "182.45",
    "stopLoss": {
        "type": "trailing_stop",
        "trailPrice": "5.00"
    }
}
```
