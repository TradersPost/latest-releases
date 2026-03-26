# June 3rd, 2025

## Improvements

Improved the ProjectX integration to display only active accounts when connecting ProjectX to TradersPost. Previously, inactive accounts were also shown.

<figure><img src="../.gitbook/assets/Screenshot 2025-06-03 at 5.28.14 PM.png" alt=""><figcaption></figcaption></figure>

Updated the default ticker from `NQ` to `MNQ` for futures strategies with `Allow any ticker` enabled. This affects the example orders and the default ticker shown when submitting a signal. You can still choose a different ticker manually.

<figure><img src="../.gitbook/assets/Screenshot 2025-06-03 at 5.30.09 PM.png" alt=""><figcaption></figcaption></figure>

Add shortcut to the dashboard to connect a paper or live prop firm account. When you use this shortcut, it takes you directly to the choose a broker flow with the prop firms filter applied.

<div><figure><img src="../.gitbook/assets/Screenshot 2025-06-03 at 5.30.57 PM.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/Screenshot 2025-06-03 at 5.31.04 PM.png" alt=""><figcaption></figcaption></figure></div>

Improved the Submit Signal interface to clearly display the selected ticker and added a simpler way to switch tickers.

<figure><img src="../.gitbook/assets/Screenshot 2025-06-03 at 5.32.29 PM.png" alt=""><figcaption></figcaption></figure>

## Bug Fixes

* Fixed a bug that caused a 500 Internal Server Error when an error response was received from the ProjectX API.
* Fixed a bug where access tokens for certain prop firm connections, such as Topstep via Tradovate, were not automatically refreshing as expected.
* Fixed a  bug with ProjectX point value being set to tick value incorrectly.
