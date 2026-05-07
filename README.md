# May 2nd, 2025

### Reject stale signals for entries and exits

You can now prevent trades from executing if a signal is too old. Configure a maximum age (in seconds) for both entries and exits, and TradersPost will ignore signals that exceed this threshold after any configured delay.

The staleness check uses the webhook `time` (if provided) or the receive time by default, helping protect against delayed alerts from TradingView or other systems. You can also allow per-signal overrides using `rejectAfter` in the webhook payload.

This gives you tighter control over execution timing and helps avoid entering or exiting positions based on outdated signals.

**Example webhook payload**

```json
{
    "ticker": "SPY",
    "action": "buy",
    "orderType": "market",
    "time": "2026-04-23 10:00:00",
    "rejectAfter": 10
}
```

### Improved subscription flow

Subscribing to a strategy is now faster and more intuitive with a streamlined 3-step flow:

1. **Choose Strategy** – Select the strategy you want to subscribe to.
2. **Choose Account** – Pick the account you want to connect to the strategy.
3. **Confirm** – Review your selections and create the subscription.

This updated flow makes it easier to understand what you’re connecting and reduces friction when getting started with a new strategy.

<div><figure><img src=".gitbook/assets/Screenshot 2026-05-07 at 8.43.56 AM.png" alt=""><figcaption></figcaption></figure> <figure><img src=".gitbook/assets/Screenshot 2026-05-07 at 8.44.15 AM.png" alt=""><figcaption></figcaption></figure> <figure><img src=".gitbook/assets/Screenshot 2026-05-07 at 8.44.21 AM.png" alt=""><figcaption></figcaption></figure></div>

### Wait to start trial until first trade

Free trials can now begin only after your first trade is submitted.

New accounts that are eligible for a free trial will start in a waiting state, so the trial clock does not begin immediately. The trial automatically starts when your first qualifying trade is submitted through a connected third-party broker.

This ensures your trial time is used while you are actively trading, instead of expiring before you’ve had a chance to use the platform.

**How it works:**

* Trial remains in a waiting state until your first trade
* Only trades submitted to third-party brokers count (TradersPost Paper trades are excluded)
* Trial starts automatically on the first qualifying trade
* No change if the trial is already started, paused, or the account is on a paid or complimentary plan
