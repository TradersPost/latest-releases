# February 19, 2022

## Feature Enhancements

Allow strategies to be privately shared with specific accounts. This is useful if you have a strategy you want to share with your friends but you don't want to make it public for everyone to subscribe to.

![Manage Strategy Access Controls](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.24.27 PM.png>)

Improve user interface and messaging when enabling and disabling strategy subscriptions.

![Disable Strategy Subscription](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.26.37 PM.png>)

Show list of subscriptions to your strategy. Previously we only showed you a count of subscriptions created but now you can see a list of who is subscribed.

![Strategy Subscribers List](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.27.58 PM.png>)

Add ability to send an email message to all of your strategy subscribers.

![Send Strategy Subscribers a Message](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.28.28 PM.png>)

Add ability to see a list of Trades for a broker connection with ability to filter by strategy subscription, ticker, etc.

![View Broker Connection Trades List](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.30.08 PM.png>)

Improve user interface of page for viewing a webhook log.

![View Webhook Request Log Screen](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.31.05 PM.png>)

Add link to broker log view screen from the order view screen.

![View Order Screen](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.32.18 PM.png>)

Add link to the order log view screen from the broker log view screen.

![View Broker Log Screen](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.35.33 PM.png>)

Improve Option Chain user interface to highlight ITM contract rows with a different color and link to View Quote screen from the option chain row.

![](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.37.09 PM.png>)

Improve Positions List UI to make better use of screen real estate.

![](<../.gitbook/assets/Screen Shot 2022-02-19 at 12.36.29 PM.png>)

## Bug Fixes

* Fix issue with option chain scanning. Sometimes brokers will return the option chain data properly sorted by expiration date and strike price and other times they will not. This would cause the option chain scanning functionality to select the wrong contract at times, so we implemented sorting on our side to ensure consistent results.
* Fix issue with option chain scanning not selecting the right contract when selecting different variations of ITM/OTM and Both/Calls/Puts.

