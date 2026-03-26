# April 13th, 2024

## Tradovate Improvements

In this release, we added support for the ability to send a take profit and stop loss to Tradovate with your entry order. Just like with other brokers, you can send a `takeProfit` and `stopLoss` along with your entry order signal.

```json
{
    "ticker": "MNQ",
    "action": "buy",
    "price": 18179.25,
    "takeProfit": {
        "limitPrice": 18200.00
    },
    "stopLoss": {
        "type": "stop",
        "stopPrice": 18000.00
    }
}
```

You can read more about sending [take profits](https://docs.traderspost.io/docs/core-concepts/webhooks#signal-take-profit) and [stop losses](https://docs.traderspost.io/docs/core-concepts/webhooks#signal-stop-loss) in our documentation.

## Audit Log

To better keep track of the history of changes made to strategies, webhooks, subcriptions and other account related data, we've added an Audit Log that can be found under your user menu at the top right of the application.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-13 at 10.53.41 AM (1).png" alt=""><figcaption><p>TradersPost Audit Log</p></figcaption></figure>
