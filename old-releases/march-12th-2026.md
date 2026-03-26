# March 12th, 2026

### Risk percent

We introduced a new dynamic method for calculating trade quantities, similar to risk amounts, which calculates the amount based on a percentage of your total account equity. Here's an example using `1%` of your account equity:

```json
{
    "ticker": "TSLA",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 100,
    "quantityType": "risk_percent",
    "quantity": 1,
    "stopLoss": {
        "stopPrice": 90
    }
}
```

For an account equity of `$10,000` with a risk percent of `1%`, the calculated risk amount would be `$100`. If entering a trade with a limit price of `$100` and a stop loss of `$90`, it would calculate a quantity of `10`.

{% hint style="info" %}
This feature is only supported by the stocks, options and crypto asset classes. Futures is currently not able to support the dynamic quantity calculation methods: `dollar_amount`, `risk_dollar_amount`, `risk_percent` and `percent_of_equity`.
{% endhint %}

### Cancel by order type

You can now specify an optional `cancelOrderType` when canceling orders. This filters the cancellation to only orders of a specific type. For example:

```json
{
    "ticker": "TSLA",
    "action": "cancel",
    "cancelOrderType": "stop"
}
```

In this example, only open TSLA orders classified as `stop` (stop market) will be canceled.
