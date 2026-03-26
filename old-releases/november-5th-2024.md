# November 5th, 2024

## Continuous Contract Symbol Validation

We’ve added validation to disallow continuous contract symbols in the list of allowed tickers for strategies or subscriptions. Using continuous contracts like `MNQ1!` will prevent trades from executing, regardless of the ticker sent through the webhook. Instead, specify the exact contract, such as `MNQZ2024`, or use `MNQ` to allow any MNQ contract. This update clarifies the current limitations of our system and aims to make TradersPost's behavior clearer.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
