---
description: >-
  It is responsible for facilitating and executing swaps against the PancakeSwap
  V3 liquidity pools.
---

# V3SwapRouter

The PancakeSwap V3 Swap Router is a contract that allows users to execute swaps on PancakeSwap V3 in a stateless manner. This means that users do not need to keep track of the state of the swap, such as the current price of the tokens being swapped. Instead, the router will take care of all of this for them.s

The router has a number of functions that can be used to execute swaps. These functions include:

* `exactInputSingle()`: This function allows users to swap a fixed amount of one token for an exact amount of another token.
* `exactInput()`: This function allows users to swap a fixed amount of one token for the best possible amount of another token.
* `exactOutputSingle()`: This function allows users to swap a fixed amount of one token for a fixed amount of another token.
* `exactOutput()`: This function allows users to swap the best possible amount of one token for a fixed amount of another token.

These functions can be used to execute a wide variety of swaps, including simple swaps between two tokens, complex swaps involving multiple tokens, and swaps that involve specific price limits.

The router also has a number of other functions that can be used to manage swaps. These functions include:

* `refundETH()`: This function allows users to refund any ETH that was sent to the router but was not used in a swap.
* `cancelSwap()`: This function allows users to cancel a swap that is in progress.
* `setOracle()`: This function allows users to set the oracle that the router will use to calculate the price of tokens.
* **pancakeV3SwapCallback()**: This function is called by the PancakeSwap V3 pool when a swap is completed. It is responsible for handling the results of the swap, such as paying out the user's tokens or refunding any unused ETH.
* **exactInputInternal()**: This function is responsible for executing a single exact input swap. It takes the amount of input tokens, the recipient of the output tokens, and the sqrt price limit as parameters and returns the amount of output tokens received.
* **exactOutputInternal()**: This function is responsible for executing a single exact output swap. It takes the amount of output tokens, the recipient of the output tokens, and the sqrt price limit as parameters and returns the amount of input tokens required.

These functions are used by the other functions in the PancakeSwap V3 Swap Router to execute swaps. For example, the `exactInput()` function calls the `exactInputInternal()` function to execute a single exact input swap, and then it calls the `pancakeV3SwapCallback()` function to handle the results of the swap.

\
