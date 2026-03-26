# August 23rd, 2024

## Webull Beta

We made the [Webull](https://traderspost.io/broker/webull) integration available for all TradersPost customers. Please remember that this integration is in <mark style="color:orange;">**BETA**</mark> and you may experience issues that we have not discovered yet. Read more about this integration in the [Webull Documentation](https://docs.traderspost.io/docs/core-concepts/brokers/broker-roadmap/webull). If you have any issues or questions, please email us at [support@traderspost.io](mailto:support@traderspost.io)

## Fix Renamed Kraken Pairs

Kraken renamed the assets `XDG` to `DOGE` and `XBT` to `BTC`. This change updates the Kraken integration to use the newly updated names. The old names will not be supported at all once this change is live in production.

## Fix Unsupported Asset Class Error

Fix fatal error when you send a symbol for an asset class that the strategy subscription or connected broker does not support. This is rare and would only happen if you for example setup a strategy subscription for futures, then change the webhook to crypto and sent a crypto symbol. You would previously get a non-descriptive unexpected error. After this change you get a specific error telling you that the asset class is unsupported.

## Case Insensitive Webhook JSON

To make TradersPost more flexible, we made the webhook JSON case insensitive. For example, `limitprice` is now the same as `limitPrice` or `LIMITPRICE`. It is recommended to use the correct casing, but if you make a mistake with the casing, it will be allowed.

## Increase Basic Plan Limits

The basic plan can now have 2 live connected brokers and can trade 2 asset classes. Previously, you could only connect 1 live broker and trade 1 asset class.&#x20;
