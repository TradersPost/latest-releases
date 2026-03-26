# June 1st, 2024

{% embed url="https://www.youtube.com/watch?v=Jye8GzwuE4c" %}

## Kraken Beta

We made the [Kraken](https://traderspost.io/broker/kraken) integration available for all TradersPost customers. Please remember that this integration is in <mark style="color:orange;">**BETA**</mark> and you may experience issues that we have not discovered yet. It is recommended to test with a paper account first. Read more about this integration in the [Kraken Documentation](https://docs.traderspost.io/docs/core-concepts/brokers/broker-roadmap/kraken). If you have any issues or questions, please email us at [support@traderspost.io](mailto:support@traderspost.io)

## Alpaca Options Beta

We've added initial support for Alpaca Options in <mark style="color:orange;">**BETA**</mark>. You can read more about Alpaca options [here](https://alpaca.markets/options). If you have an existing Alpaca account connected to TradersPost, you will need to reconnect the account in order to enable options support. All new Alpaca accounts that get connected to TradersPost will have support for options.

## Use Signal Settings Enabled By Default

All signal settings will be used by default and to ignore the signal settings, you will have to uncheck the `Use signal settings` checkbox. We decided that it was better to be enabled by default since most people will want to use the settings from the signal. If you are using a strategy with hardcoded JSON, you can uncheck `Use signal settings` and then configure your own settings in your strategy subscription. All existing strategy subscriptions will have `Use signal settings` disabled, but new strategies and subscriptions created after today will have it enabled by default.

## Add orderType to Webhook

You can now control the order type from webhooks with the new field named `orderType`. The `orderType` field is optional. If not specified, the default order type configured in your strategy subscription settings will be applied. The supported values for the `orderType` field are:

* market
* limit
* stop\_limit
* stop
* trailing\_stop

### Market Order

```json
{
    "ticker": "SQ",
    "action": "buy",
    "orderType": "market"
}
```

### Limit Order

A limit order allows you to specify the maximum price you are willing to pay when buying a stock, or the minimum price you are willing to accept when selling a stock. This ensures that you do not pay more or receive less than this specified price for the stock.

For example, to set up a limit order to buy the ticker symbol `SQ` at a maximum price of `$200`, you would use the following JSON structure:

```json
{
    "ticker": "SQ",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 200
}
```

### Stop Limit Order

A stop limit order combines the features of a stop order and a limit order. When you place a stop limit order, you specify two prices: the `stopPrice` and the `limitPrice`. The order will only be executed at the specified limit price or better, but only after the stock price reaches the stop price. This type of order gives you control over the price at which the order should be executed, helping to limit losses or protect profits.

For example, to place a stop limit order for the ticker symbol `SQ` to buy at a limit price of `$200` only after the price rises to `$201`, you would use the following JSON structure:

```json
{
    "ticker": "SQ",
    "action": "buy",
    "orderType": "stop_limit",
    "stopPrice": 201,
    "limitPrice": 200
}
```

In this example, the `action` is set to "buy," indicating a purchase. The `orderType` is `stop_limit`, specifying that this is a stop limit order. The `stopPrice` is set at `$201`, which is the price the stock must reach before your limit order is placed. Finally, the `limitPrice` is set at `$200`, indicating the maximum price you are willing to pay per share.

### Trailing Stop Order

In this example, the `orderType` is `trailing_stop`, featuring a `trailPercent` of `2%`. This configuration means that the order to sell the stock will activate when its price falls `2%` below its peak value since the order's initiation. This mechanism allows investors to safeguard their gains by setting up an automatic sell trigger in response to price declines.

```json
{
    "ticker": "SQ",
    "action": "sell",
    "orderType": "trailing_stop",
    "trailPercent": 2
}
```

Instead of a percentage, you can specify a trailing stop order with a fixed dollar amount using the `trailAmount` field. This means the order will be executed once the asset's price moves against the direction of the trade by the specified dollar amount from its peak value since the order was placed.

```json
{
    "ticker": "SQ",
    "action": "sell",
    "orderType": "trailing_stop",
    "trailAmount": 5
}
```

In this example, buying `MSFT` stocks is triggered when their price decreases by `$5` from the highest price since the order was placed. This method is particularly useful for stocks with higher volatility, as it allows for more precise control over the execution price.

{% hint style="info" %}
Note that if you are using Tradovate, you must include a `signalPrice` in your JSON to be able to calculate the starting trailing stop price correctly for Tradovate.

```json5
{
    "ticker": "SQ",
    "action": "sell",
    "orderType": "trailing_stop",
    "signalPrice": 100,
    "trailAmount": 5
}
```
{% endhint %}

## Add quantityType to Webhook

With the introduction of the `quantityType` field in the webhook, you can now control the dynamic calculation methods for quantities previously only available from within your strategy subscription settings. Below are the allowed values for `quantityType` and examples for each.

* [fixed\_quantity](june-1st-2024.md#fixed-quantity)
* [dollar\_amount](june-1st-2024.md#dollar-amount)
* [risk\_dollar\_amount](june-1st-2024.md#risk-dollar-amount)
* [percent\_of\_equity](june-1st-2024.md#percent-of-equity)
* [percent\_of\_position](june-1st-2024.md#percent-of-position)

### Fixed Quantity

The fixed quantity is the simplest quantity type. In this example it will simply buy 10 shares of AAPL.

```json
{
    "ticker": "AAPL",
    "action": "sell",
    "quantityType": "fixed_quantity",
    "quantity": 10
}
```

### Dollar Amount

In this example it will buy `$10000` worth of `AAPL`. If the current price of `AAPL` Is `$100`, then it will calculate a quantity of `100`.

```json
{
    "ticker": "AAPL",
    "action": "buy",
    "quantityType": "dollar_amount",
    "quantity": 10000
}
```

### Risk Dollar Amount

In this example it will buy `10` shares because we've said that the most we want to be able to lose is `$100`. If we get filled at `$180` and we have a stop loss at `$170`, then if we get stopped out we'll lose `$10` per share, which means we can afford to buy `10` shares.

```json
{
    "ticker": "AAPL",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 180,
    "quantityType": "risk_dollar_amount",
    "quantity": 100,
    "stopLoss": {
        "type": "stop",
        "stopPrice": "170"
    }
}
```

### Percent of Equity

In this example, if you have a `$100000` account and you want to buy `AAPL` using `10%` of your total equity, and your `limitPrice` is `$100`, then it will calculate a quantity of `100` shares.

```json
{
    "ticker": "AAPL",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 100,
    "quantityType": "percent_of_equity",
    "quantity": 10
}
```

### Percent of Position

In this example, we are selling `50%` of the open `AAPL` position. If the total quantity of the `AAPL` position was `100` shares, then it would calculate a quantity of `50`.

```json
{
    "ticker": "AAPL",
    "action": "sell",
    "quantityType": "percent_of_position",
    "quantity": 50
}
```

## Control Option Chain Scanning From Webhook

You can now control the option chain scanning functionality from webhooks! In this example, it will buy SPY calls that expire in `6` months, are in the money and are `2` strikes away from at the money. It will calculate a quantity dynamically for `$1000` worth of calls.

```json
{
    "ticker": "SPY",
    "action": "buy",
    "expiration": "+6 months",
    "optionType": "call",
    "intrinsicValue": "itm",
    "strikesAway": 2,
    "quantityType": "dollar_amount",
    "quantity": 1000
}
```

## Send Specific Options Contract From Webhook

You can directly send a specific options contract symbol via the webhook, eliminating the need to scan the option chain to find a contract to trade.

To send a specific options contract through the webhook, include the contract symbol in the `ticker` field in your payload. This field should contain the full symbol of the option contract you wish to trade. Here's an example of how to structure your payload:

```json
{
  "ticker": "SPY 240510C516",
  "quantity": 1
}
```

In this example, `SPY 240510C516` represents the symbol for a specific SPY contract. The structure of this symbol is broken down as follows:

* **SPY** is the underlying asset.
* **240510** indicates the expiration date, which is the `10th of May, 2024`.
* **C** signifies a Call option.
* **516** refers to the strike price of `$516`.

By specifying the contract symbol in this manner, you ensure that the exact desired options contract is selected for trading, bypassing the need to scan the option chain to find a contract dynamically. You can manually pick which contract you want to trade ahead of time and keep it up to date as contracts expire.

You can also optionally specify the specific contract to trade with individual field instead of using the symbol format in the `ticker` field.

```json
{
  "ticker": "SPY",
  "action": "buy",
  "expiration": "2024-05-10",
  "optionType": "call",
  "strikePrice": 516
}
```

## Strategy Subscription Settings Improvements

In addition to being able to control more order attributes from webhooks, you can also control them from strategy subscriptions with the following new settings.

* Entry order type
* Entry time in force
* Exit order type
* Exit time in force

You will see these new settings in the `Entry` and `Exit` sections when editing a strategy subscription.

## Give Feedback on Option Chain Scanning

The option chain scanning feature now includes a snapshot of the option chain at the moment a trade was executed. This allows users to visually see the selected contract according to their configured settings. You will see this option chain snapshot when editing your strategy subscription and when you are viewing an individual subscription trade.

<figure><img src="../.gitbook/assets/Screenshot 2024-05-10 at 1.56.51 PM.png" alt=""><figcaption></figcaption></figure>

## Send Options Prices in Webhooks

You can now send prices in webhooks for options trades. Previously, if you were to send a `limitPrice` for an options trade, it would be ignored and we would always fetch a quote and use the price from the quote for the `limitPrice`.

```json
{
  "ticker": "SPY 240510C516",
  "quantity": 1,
  "orderType": "limit",
  "limitPrice": 1.2
}
```

This feature is disabled for all existing options strategy subscriptions that predate this feature and is enabled for all new strategy subscriptions created after this change. You can enable and disable this feature in the `Entry` or `Exit` sections when editing your settings.

<figure><img src="../.gitbook/assets/Screenshot 2024-05-14 at 2.06.35 PM.png" alt=""><figcaption></figcaption></figure>

## Control Quote Price Used

You can now control which quote price is used when calculating entry and exit orders. Prior to this change, it would always use the `Bid-ask midpoint` price. You can now control this explicitly for entries and exits under the `Entry` and `Exit` sections using the `Entry market price type` and `Exit market price type` dropdown. The allowed options are:

* Bid-ask midpoint (default)
* Use ask for buys and bid for sells
* Always use ask
* Always use bid
* Use last price

## Signal Price

We introduced a new webhook JSON field named `signalPrice` which can contain the current market price at the time the signal was generated. In the cases where we are not able to fetch a quote from the broker we will use the `signalPrice` in place of the quote. This addition is mainly relevant for Tradovate which does not support fetching quotes, so you always need to send a `signalPrice` with your signal to be able to perform relative price calculations.

Here is an example where we are executing a market buy order with a relative `$5` trailing stop loss attached to the entry. To be able to calculate the initial stop price to send to Tradovate, we need a price to base our calculation off of. In this example we will use the `signalPrice` with a value of `$100` and it will calculate an initial stop price of `$95`.

```json
{
    "ticker": "SQ",
    "action": "buy",
    "orderType": "market",
    "signalPrice": 100,
    "stopLoss": {
        "type": "trailing_stop",
        "amount": 5
    }
}
```

## Add Tradovate Trailing Stops

Tradovate now support trailing stops. Since Tradovate does not support fetching quotes, you will need to include a `signalPrice` in your webhook JSON so that we are able to calculate your orders correctly. In the below example, we will calculate the starting trailing stop price as `$18350`.

```json
{
    "ticker": "MNQ",
    "action": "buy",
    "orderType": "trailing_stop",
    "signalPrice": 18250,
    "trailAmount": 100
}
```

Or if you want to send a percentage instead of a fixed dollar amount, you can do that as well using the trailPercent field.

```json5
{
    "ticker": "MNQ",
    "action": "buy",
    "orderType": "trailing_stop",
    "signalPrice": 18250,
    "trailPercent": 5
}
```

You can also send trailing stop orders along with your entry order as well. In the below example, the entry order will be a limit order with a limit price of `$18250` and a trailing stop order with a starting trailing stop price of $1`8150`.

```json
{
    "ticker": "MNQ",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 18250,
    "stopLoss": {
        "type": "trailing_stop",
        "trailAmount": 100
    }
}
```

Or with a percent instead of an amount.

```json
{
    "ticker": "MNQ",
    "action": "buy",
    "orderType": "limit",
    "limitPrice": 18250,
    "stopLoss": {
        "type": "trailing_stop",
        "trailPercent": 100
    }
}
```

## Add Use Signal Settings Checkbox

You can now opt in to all signal settings with one checkbox named **Use signal settings** instead of having to opt in to each one individually. This setting is enabled by default too. So by default, signal settings will be used unless you turn it off.

<figure><img src="../.gitbook/assets/Screenshot 2024-05-13 at 4.30.35 PM.png" alt=""><figcaption></figcaption></figure>

## Rename trailPrice to trailAmount

When sending a webhook with a stop loss, use the `trailAmount` field to specify a relative trail dollar amount. This naming was updated from `trailPrice` to better reflect that it represents a relative dollar amount instead of an absolute price.

```json
{
    "ticker": "SQ",
    "action": "buy",
    "stopLoss": {
        "type": "trailing_stop",
        "trailAmount": 10
    }
}
```

{% hint style="info" %}
While we will continue to support `trailPrice` for backward compatibility, we recommend using `trailAmount` for future implementations.
{% endhint %}

