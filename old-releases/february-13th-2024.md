# February 13th, 2024

## Improvements

* In this release we made a change to the Interactive Brokers integration so that only one trade can be executed in parallel per IBKR user. This is due to a limitation with the IBKR API where they are not able to execute multiple trades in parallel and it would frequently cause API calls to timeout. Now if you send multiple trades at the same time, we will only execute them one at a time.
