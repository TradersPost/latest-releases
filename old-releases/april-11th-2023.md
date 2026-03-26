# April 11th, 2023

In this release we added the ability to disable a strategy at the strategy level. Disabling a strategy will cause all strategy subscriptions to effectively be disabled. Any strategy webhook signals that are received while the strategy is disabled will not result in any executed trades for all strategy subscriptions. You can easily re-enable a strategy after disabling and strategy subscriptions will begin executing trades again.

You will now see a new **Disable** button when viewing your list of strategies.

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-11 at 3.47.29 PM.png" alt=""><figcaption><p>TradersPost Strategies List Screen</p></figcaption></figure>

The **Disable** button also appears when editing a strategy as well.

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-11 at 3.47.36 PM.png" alt=""><figcaption><p>TradersPost Strategy Edit Screen</p></figcaption></figure>
