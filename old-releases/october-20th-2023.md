# October 20th, 2023

## IBKR Quote Support

In this release we added quote support to the Interactive Brokers integration. We will now make an attempt to fetch a quote from IBKR and if we cannot get a quote from IBKR, we will fallback to the Polygon market data provider. This makes the functionality that depends on quotes functional within the IBKR integration. For example, you can now dynamically calculating quantities in your strategy subscription settings with the IBKR integration. You can read more about how the quotes functionality works for IBKR [here](https://docs.traderspost.io/docs/brokers/interactive-brokers#market-data-quotes).
