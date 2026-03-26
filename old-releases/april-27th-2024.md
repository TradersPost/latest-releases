# April 27th, 2024

## Improved Crypto Quote Currency Support

In this release, we improved support for quote currencies when trading crypto. In addition to selecting your default quote currency on your connected account, you can select a quote currency to quote your open positions in when viewing the positions list.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-27 at 9.20.40 AM.png" alt=""><figcaption></figcaption></figure>

This also means you can buy/sell with any supported quote currencies when sending webhooks to TradersPost. For example, say you have some `ETH` and you want to sell it to `USDC`, you can simply send the ticker `ETH-USDC` in your webhook and we will quote the `ETH` in `USDC` and sell it to `USDC`.

Or if you want to buy `ETH` using your `USDT` balance, then you can send `ETH-USDT` in your webhook. Here are some examples:

Buy `ETH` using your `USDT` account:

```json5
{
    "ticker": "ETH-USDT",
    "action": "buy"
}
```

Sell `ETH` in to your `USDC` account:

```json5
{
    "ticker": "ETH-USDC",
    "action": "sell"
}
```

## Bybit Crypto Exchange Beta

We made the [Bybit](https://traderspost.io/broker/bybit) integration available for all TradersPost customers. Please remember that this integration is in <mark style="color:orange;">**BETA**</mark> and you may experience issues that we have not discovered yet. It is recommended to test with a paper account first. Read more about this integration in the [Bybit Documentation](https://docs.traderspost.io/docs/core-concepts/brokers/bybit). If you have any issues or questions, please email us at [support@traderspost.io](mailto:support@traderspost.io)

## Fixed Tradier Bug With Limit Sell Short

In this release we fixed a bug with the Tradier integration where limit sell short orders were being sent with a Good Until Canceled (GTC) time in force, which Tradier rejects. For Tradier only, we will now send DAY instead of GTC when it is a limit sell short order.

## Portfolio Analytics

In this release, we made available some initial portfolio analytics that you can find on the Balances page under your connected broker. We collect the balances for all of your connected accounts on a daily balance. From these daily balances, we are able to show you a nice graph along with some calculated analytics.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-27 at 9.29.09 AM.png" alt=""><figcaption></figcaption></figure>

These are the metrics we currently support:

* **Annualized Return** - This measures the percentage gain or loss of an investment over a year where returns longer than a year are averaged and returns shorter than a year are projected.
* **Cumulative Return** - The total percentage gain or loss of an investment over the entire period it's been held.
* **Annual Volatility** - Measures the standard deviation of the investment's daily returns, reflecting how much the investment's value fluctuates. Lower is generally better; < 15% is considered low, > 30% high.
* **Sharpe Ratio** - Measures risk-adjusted return; the higher, the better. > 1 is good, > 2 is very good, > 3 is excellent. Negative shows that the return risk is greater than the returns and by what degree. The risk-free rate is divided into 252 business days from an expected 2% per year.
* **Calmar Ratio** - This ratio compares the annual return to the maximum drawdown. Higher is better.
* **Stability** - Reflects the consistency of the returns. 0 to 1; closer to 1 indicates more consistency.
* **Max Drawdown** - The largest peak-to-trough decline in investment value. Smaller (less negative) is better.
* **Omega** - Compares the likelihood of gains versus losses. > 1 is favorable. The risk-free rate is divided into 252 business days from an expected 2% per year.
* **Sortino Ratio** - Similar to the Sharpe Ratio but only considers downside volatility. Higher is better; similar scale to Sharpe Ratio.
* **Tail Ratio** - The ratio of the far right (95th percentile) to the far left (5th percentile) of the return distribution. Higher than 1 is good.
* **Daily Value At Risk** - Estimates the maximum potential loss in value of a portfolio over a given time frame. Smaller (less negative) is better.
