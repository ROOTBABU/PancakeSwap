# Swap

The following folders are inside the `swap` folder:

* **components:** This folder contains reusable components that are used throughout the swap page.
* **hooks:** This folder contains custom hooks that are used throughout the swap page.
* **SwapContext.tsx:** This file contains the context provider for the `SwapContext`. This context is used to share information about the swap between different components.
* **index.tsx:** This file is the entry point for the `swap` folder. It contains the code for the main layout of the swap page.
* **styles.tsx:** This file contains the global styles for the swap page.
* **SwapFeaturesContext.tsx:** This file contains the context provider for the `SwapFeaturesContext`. This context is used to share information about the swap features between different components.

A quote is a price at which something is available to buy or sell. In the context of trading, a quote is the price at which a buyer is willing to buy an asset and the price at which a seller is willing to sell an asset.

On-chain quoting, off-chain quoting, and API quoting are three different ways to get quotes for trades on PancakeSwap.

\
**On-chain quoting** involves calling a smart contract on the blockchain to get quotes for all of the possible trades that can be executed. This is the most accurate way to get quotes, but it can also be the most expensive, as it requires gas to call the smart contract.

**On-chain quoting** involves calling the SmartRouter contract on the blockchain to get quotes for all of the possible trades that can be executed using the candidate pools. This is the most accurate method of getting quotes, but it can also be the most expensive, as it requires gas to call the SmartRouter contract.

\
**Off-chain quoting** involves using a local database to get quotes for all of the possible trades that can be executed. This method is less expensive than on-chain quoting, but it may not be as accurate, as the quotes in the local database may not be up-to-date.

**API quoting** involves calling an API to get quotes for all of the possible trades that can be executed. This method is the least expensive of the three methods, but it may not be as accurate as on-chain quoting or off-chain quoting, as the API may not be able to provide quotes for all of the possible trades or the quotes may not be up-to-date.\


Which method is best to use depends on the specific needs of the application. If the application needs the most accurate quotes possible, then on-chain quoting is the best option. If the application needs to minimize costs, then off-chain quoting or API quoting is the best option.

