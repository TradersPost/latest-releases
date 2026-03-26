# November, 15th, 2023

## Improvements & Bug Fixes

* Added visual icons in the header of form sections to visually separate them better.
* Fixed issue with collecting daily balances from Interactive Brokers connected accounts.
* Fixed issue with Users module access controls based on account billing plan.

## Enhancements

In this release we have a few different minor enhancements to address some commonly requested functionality from customers.

### Futures Contract Switching

In this release we made a change to improve how we handle continuous contract symbols and when we switch from the current contract to the next contract.

We will now switch from the current contract to the next contract two days before the beginning of the expiration date. So take `MNQZ2023` for example. It has an expiration date of **Friday December 15th, 2023**.

* Before this change, `MNQ1!` switches to `MNQH2024` at the end of **December 15th, 2023**.
* After this change, `MNQ1!` switches to `MNQH2024` at the beginning of **December 13th, 2023**.

### Market Orders and Extended Hours Orders

You can now combine market orders and extended hours orders. When the market is open, market orders will be used and when the market is closed, limit orders with extended hours enabled will be used.

Previously, you were disallowed from checking `Allow entry extended hours` when `Entry market` was checked. Now you can combine these settings and TradersPost will switch accordingly depending on if the market is open or not.

{% hint style="info" %}
You will also notice in this screenshot below that the old **Advanced Settings** section has been split in to three separate sections: **Cancel Settings**, **Entry Settings** and **Exit Settings.**
{% endhint %}

<figure><img src="../.gitbook/assets/Screenshot 2023-11-09 at 4.27.09 PM.png" alt=""><figcaption></figcaption></figure>

### Both Sides in Extended Hours

In addition to the ability to combine market and extended hours orders, you can now execute strategy subscription trades on both sides (bullish and bearish) with extended hours enabled.

When the market is closed, we will send limit orders to the broker with extended hours enabled. If the trade has both an exit and entry order, we will wait for the exit limit order to fill before sending the entry order. If the exit order does not fill within the `Exit wait timeout`, the trade will marked as failed, the entry order will not be submitted to the broker and the exit limit order will be left open. The default exit wait timeout is 120 seconds (2 minutes).

### Disable Canceling Open Orders

In the new `Cancel Settings` section, you can now control whether or not TradersPost should attempt to cancel open orders before executing a trade by checking the `Disable canceling open orders` checkbox.

{% hint style="warning" %}
Beware that if you disable this and you use take profit or stop losses in your broker and you send an exit signal, the broker may reject your exit order due to the take profit or stop loss orders still being open.
{% endhint %}

<figure><img src="../.gitbook/assets/Screenshot 2023-11-09 at 4.40.15 PM.png" alt=""><figcaption></figcaption></figure>

### Coinbase Default Quote Currency

When you connect your Coinbase account, you will see a new field called `Default Quote Currency` that allows you to set a different default quote currency than USD. Previously, it would default to `USD` and there was no way to change it. The quote currencies we currently support with Coinbase are as follows:

* USD
* USDC
* USDT
* DAI

<figure><img src="../.gitbook/assets/Screenshot 2023-11-09 at 4.33.49 PM.png" alt=""><figcaption></figcaption></figure>

### Delayed Data Warning

We will now surface some convenient UI elements whenever a quote has delayed data. It was not always so immediately obvious if a quote was realtime or delayed and you had to inspect the quote data to see if it was delayed or not.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-10 at 12.41.49 PM.png" alt=""><figcaption></figcaption></figure>
