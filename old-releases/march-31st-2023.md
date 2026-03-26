# March 31st, 2023

## TradersPost Paper Broker Market Price Type

In this release we added the ability to configure what quote price to use as the current market price when filling market orders in the TradersPost paper broker. This configured price is also used for the current price of open positions.

You can edit the **Market Price Type** by navigating to **Connected Brokers** and clicking **Edit** next to you TradersPost paper broker and selecting an option from the **Market Price Type** dropdown.

The available options are as follows:

* **Bid-ask midpoint (default)** - This option will use the midpoint between the bid price and ask price.
* **Use ask for buys and bid for sells** - This option will use the quote ask price for buys and bid price for sells.
* **Always use ask** - This option will always use the quote ask price.
* **Always use bid** - This option will always use the quote bid price.
* **Use last price** - This option will always use the quote last price.

Prior to this release, the default was always **Bid-ask midpoint** and now you can configure which price to use in your TradersPost paper broker!

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-11 at 3.37.40 PM.png" alt=""><figcaption><p>TradersPost Paper Broker Edit Screen</p></figcaption></figure>
