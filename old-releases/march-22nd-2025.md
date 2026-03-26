# March 22nd, 2025

## Improve List With Buttons Template

Improve styling of lists with buttons on mobile so there is less wrapping causing the flow of the design to be displaced.

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 11.51.09 AM.png" alt=""><figcaption></figcaption></figure>

## Contract Expiration Notice

When you view a contract in the TradersPost UI that is expiring soon, we will now show this new **Contract Expiration Notice** to let you know when the contract expires and when TradersPost will switch to the next contract.

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 11.55.28 AM.png" alt=""><figcaption></figcaption></figure>

We updated the list of active futures tickers to display the specific contract that each continuous contract symbol currently maps to. The list now also includes the switch date and expiration date for each contract

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 11.53.26 AM (1).png" alt=""><figcaption></figcaption></figure>

## Orders List Highwater Mark

We've improved our order lists to accurately display the highwater mark for trailing stop orders. The highwater mark (HWM) reflects the current value of the dynamic stop price, which adjusts as the market price changes.

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 12.00.20 PM.png" alt=""><figcaption></figcaption></figure>

## Improved Strategy Subscriptions Page

We have improved the styling and functionality of the strategy subscriptions page to enhance readability. The subscriptions list is now separated into enabled and disabled sections. You can view the disabled subscriptions by clicking on the "Disabled Subscriptions" card. Additionally, users who no longer have access to the strategy will not appear in the disabled subscriptions list, ensuring that it only displays subscriptions from users who still have access to the strategy.

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 12.03.03 PM.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2025-03-22 at 12.03.17 PM.png" alt=""><figcaption></figcaption></figure>

## Bug Fixes

* Fixed a bug with deleting users from your account.
* Corrected an issue with the `Allow entry/exit extended hours` setting, where we incorrectly sent orders to the broker with extended hours enabled when sending an order type that wasn't a market order or limit order.
