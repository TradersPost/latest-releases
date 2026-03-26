# December 21st, 2022

## Improvements

This release contains several different improvements mostly around the webhooks functionality.

### JSON5 Parser

Users commonly have issues with the JSON that gets sent to TradersPost. To improve this, we adopted a new JSON5 parser that makes the JSON that we accept a bit more flexible. For example, you can now have trailing commas in your JSON.

Before, this JSON was invalid:

```json5
{
    "ticker": "TSLA",
    "action": "buy",
}
```

Notice the trailing comma on the 3rd line. This would have caused a JSON error previously. Now it will be accepted as valid JSON. You can read more about JSON5 [here](https://json5.org/).

### JSON Parse Errors

Due to us adopting a new JSON5 parser, we are now able to provide more specific error messages to help you identify what is wrong with your JSON. We will try to point out the specific line and column where the error exists.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-27 at 10.09.55 AM.png" alt=""><figcaption><p>JSON Error</p></figcaption></figure>

### Notify Failures Only

You can now restrict notifications to only notify you of failures. If you go to your strategy subscription settings, you will see a Notifications section where you can setup your notifications.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-27 at 10.12.07 AM.png" alt=""><figcaption><p>Strategy Subscription Notification Settings</p></figcaption></figure>

### Webhook Notifications

You will now find a similar section when editing webhooks. You can configure notifications for new and failed webhooks or restrict to only failed webhooks by checking **Notify failures only**.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-27 at 10.14.51 AM.png" alt=""><figcaption><p>Webhook Notification Settings</p></figcaption></figure>

### Account Notification Settings

If you don't want to configure notification settings on each strategy subscription or webhook, under your Account Settings, you will see a new section for managing this.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-27 at 10.16.54 AM.png" alt=""><figcaption><p>Account Notification Settings</p></figcaption></figure>

### Copy Webhook URL

The copy button next to a webhook URL will actually copy the URL now without you having to copy the URL manually.

<figure><img src="../.gitbook/assets/Screen Shot 2022-12-27 at 10.21.26 AM.png" alt=""><figcaption></figcaption></figure>

