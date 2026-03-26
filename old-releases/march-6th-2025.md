# March 6th, 2025

Webhook rate limiting has been turned on. You are allowed 60 requests per minute and 500 per hour. Anyone who hits the rate limits will have requests over the rate limits blocked. It won’t show anywhere in TradingView or TradersPost that a webhook was blocked. We send this response to the webhook request with a 429 status code:

```json5
{
    "success": false,
    "messageCode": "too-many-requests",
    "message": "Too many requests. You are only allowed 60 requests per minute and 500 requests per hour."
}
```

If you send the webhook request from custom code, you will see this response but in TradingView and TrendSpider it won’t show up anywhere unless you reach out to support to ask why a webhook request didn't make it to TradersPost.

Most people should never be hitting these rate limits under normal circumstances. You can read more about our rate limits here: [https://docs.traderspost.io/docs/learn/rate-limits](https://docs.traderspost.io/docs/learn/rate-limits)

Next, we plan to enable notifications via email and in the TradersPost interface to let you know whenever a strategy webhook is rate limited.
