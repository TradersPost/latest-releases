# September 3rd, 2023

## New Broker Integrations

In this release we added support for **Interactive Brokers** and **Coinbase**. These integrations are currently hidden and are only available to beta testers. If you would like to be a beta tester, please email us at [support@traderspost.io](mailto:support@traderspost.io).

## Show timezone next to dates

This is useful so that you can visually see the timezone a date is in. You can control the timezone that dates show in by going to My Account > Settings within TradersPost and choosing a different timezone.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-05 at 12.50.30 PM.png" alt=""><figcaption></figcaption></figure>

## Trade Retries

Added ability to retry trades that fail during trade planning. You can configure how many times to retry and how long to wait in between retries. This will only retry a trade if an API call fails when communicating with the broker during trade planning, it will not retry trades if the API fails after trade planning during execution. For example, if the broker API fails when we send an exit or entry order, we will not retry the trade. This is because we don't have a way currently to guarantee that the order creation did not actually succeed, even though we received a failure response back from the broker.

<figure><img src="../.gitbook/assets/Screenshot 2023-08-28 at 1.57.52 PM.png" alt=""><figcaption></figcaption></figure>

## TradersPost Paper Broker Market Price

We changed the TradersPost paper broker to default to use the last price as market price by default instead of the midpoint price. You can control this setting by clicking the Edit button next to your TradersPost paper broker and selecting a different option from the **Market Price Type** dropdown. This change only affects TradersPost paper brokers that have not already selected a custom option from the Market Price Type dropdown.

## Trade Quote Button

We added a **Quote** shortcut button to view the quote used for a trade when viewing the trade. This was already available by clicking the **Debug** button at the bottom of the page but we added a **Quote** button so you can quickly view the quote used for the trade.

<figure><img src="../.gitbook/assets/Screenshot 2023-08-28 at 3.00.20 PM.png" alt=""><figcaption></figcaption></figure>

## Order History Asset ID&#x20;

This is a useful little convenience feature that we added so that you can see the broker specific Asset ID for an order. In the below screenshot, we show an order for the option contract **FSLY 230908C21.5** which is shown in the TradersPost option symbol format. Underneath it, you will now see a new **Asset ID** field that contains the symbol in the brokers format.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-05 at 12.45.02 PM.png" alt=""><figcaption></figcaption></figure>

We also now show this **Asset ID** on the quote page.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-05 at 12.48.47 PM.png" alt=""><figcaption></figcaption></figure>

## Trade Configuration UI Improvement

We improved the UI of the **Trade Configuration** section when viewing an individual trade. Previously this section listed all of the values but did not organize them in to the same sections the settings are organized in when editing strategy subscription settings.

This table of data contains the settings of the strategy subscription at the time the trade was created so you can easily see what the settings values were at the time the trade was executed.

<figure><img src="../.gitbook/assets/Screenshot 2023-09-05 at 12.54.54 PM.png" alt=""><figcaption></figcaption></figure>
