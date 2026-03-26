# October 21st, 2022

## Improvements

This release contains improvements to the webhook payload to support sending optional take profit and stop loss information in the signal as well as a few other minor improvements.

### Take Profit & Stop Loss in Webhook

{% embed url="https://www.youtube.com/watch?v=OWprbGx4_iM" %}

Here is a simple example that shows how you can include a take profit limit price and a stop loss stop price with your entry signal.

```json
{
   "ticker": "TSLA",
   "action": "buy",
   "price": 420.69,
   "takeProfit": {
       "limitPrice": 450.22
   },
   "stopLoss": {
       "stopPrice": 400.20
   }
}
```

#### Relative Percent Take Profit & Stop Loss

You can pass a percentage for TradersPost to use to calculate the take profit limit price and stop loss stop price.

```json
{
   "ticker": "TSLA",
   "action": "buy",
   "price": 420.69,
   "takeProfit": {
       "percent": 10
   },
   "stopLoss": {
       "percent": 5
   }
}
```

#### Relative Amount Take Profit & Stop Loss

Or you can pass a dollar amount for TradersPost to use to calculate the take profit limit price and stop loss stop price.

```json
{
   "ticker": "TSLA",
   "action": "buy",
   "price": 420.69,
   "takeProfit": {
       "amount": 50
   },
   "stopLoss": {
       "percent": 10
   }
}
```

### Webhook Send Request

The **Send Request** functionality under webhooks has been updated to allow you to send a take profit and stop loss in your signal as well.

<figure><img src="../.gitbook/assets/Screen Shot 2022-10-21 at 10.47.29 AM.png" alt=""><figcaption></figcaption></figure>

The **Send Request** functionality now has a confirm screen so you can review the JSON payload before sending it to the webhook.

<figure><img src="../.gitbook/assets/Screen Shot 2022-10-21 at 10.53.11 AM.png" alt=""><figcaption></figcaption></figure>

### Dollar Amount Take Profit & Stop Loss

In addition to the take profit and stop loss percent functionality, you can now configure a take profit or stop loss using a dollar amount instead of a percent.

<figure><img src="../.gitbook/assets/Screen Shot 2022-10-21 at 10.48.56 AM.png" alt=""><figcaption></figcaption></figure>

### Trade Configuration

On the trade screen you will now see a new section called **Trade Configuration** that shows the configuration used to executed the trade. Each trade that gets executed copies the settings from the strategy subscription so you can see what settings were used to execute a trade if you change the settings in your strategy subscription.

<figure><img src="../.gitbook/assets/Screen Shot 2022-10-21 at 10.40.46 AM.png" alt=""><figcaption></figcaption></figure>

