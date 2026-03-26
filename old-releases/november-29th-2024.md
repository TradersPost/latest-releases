# November 29th, 2024

Fixed a bug in Tradovate symbol parsing where symbols such as `CLF5` were incorrectly parsed as `CLF2024` instead of `CLF2025`. The issue arose because Tradovate uses a single-digit year like `5` to denote `2025`, and our logic incorrectly utilized only the expiration year, leading to the error. This problem only affected contract symbols where the symbol year differs from the expiration year.
