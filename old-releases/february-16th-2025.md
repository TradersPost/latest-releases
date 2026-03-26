# February 16th, 2025

## Improved Ticker Symbol Format Validation

We enhanced ticker symbol validation across the application to ensure more accurate format checks and provide clearer error messages when the symbol format is invalid.

<figure><img src="../.gitbook/assets/Screenshot 2024-09-25 at 6.40.45 PM.png" alt=""><figcaption></figcaption></figure>

## New Strategy Fields

We've introduced two new fields to the strategy form: `Style` and `Allow Auto Submit`. Below, you'll find detailed information about these fields, along with a screenshot for reference.

<figure><img src="../.gitbook/assets/Screenshot 2024-09-25 at 6.17.15 PM.png" alt=""><figcaption></figcaption></figure>

### Style

We’ve added a new `Style` field to strategies, offering two options: `Systematic` and `Discretionary`. Currently, this field is used for data collection to better understand how users are leveraging TradersPost. In future updates, we plan to incorporate this field into new features, particularly to enhance support for discretionary traders.

### Allow Auto Submit

The `Allow auto submit` option provides strategy owners with greater control over how their strategies are utilized by subscribers. When this option is disabled, subscriptions will not be allowed to enable auto submit on their strategy subscriptions and they will have to manually approve or reject the trades.

### Allow Live Trading

The `Allow live trading` option gives strategy owners control over whether their strategy can be used with live broker accounts. When this option is disabled, subscribers will only be able to use paper trading accounts with the strategy.
