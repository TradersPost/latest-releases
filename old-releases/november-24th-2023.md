# November 24th, 2023

## Bug Fixes

* Fix generic 500 error when trying to connect a broker while the broker API is unavailable. We will now show a proper error message about the communication problem with the broker instead of a generic 500 error.
* Fix issue with trade retries where a trade may not be retried the maximum number of retries configured.

## Trading Windows

You now have the ability to ignore trades outside of a defined trading window. In the strategy settings, you will see a new section named **Trading Window Settings** where you can define multiple trading windows. If a trade is executed outside of the defined trading windows, then the trade will be ignored. These ignored trades will show up in the trades interface with a new status named "Ignored" so you can search for them and see when you are sending trades outside of your configured trading windows.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-16 at 8.50.38 AM.png" alt=""><figcaption></figcaption></figure>

## Improve Strategy Subscription Disabled Message

This is a minor improvement but some users would get stuck and not see the green Enable button at the top right, so we improved the messaging here and added another Enable button next to the message to make it more clear.

<figure><img src="../.gitbook/assets/Screenshot 2023-11-16 at 10.56.28 AM.png" alt=""><figcaption></figcaption></figure>
