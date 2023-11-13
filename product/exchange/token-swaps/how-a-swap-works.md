# How a swap works

Step by step, following the path from user to liquidity pool:

1. **User:** The user calls the `swapExactTokensForTokens()` function on the PancakeRouter03 contract, specifying the amount of tokens they want to sell, the minimum amount of tokens they want to receive, the path of tokens they want to trade, the recipient address, and the deadline for the trade.
2. **PancakeRouter03:** The PancakeRouter03 contract interacts with the FactoryV3 contract to find the best liquidity pool for the trade.
3. **FactoryV3:** The FactoryV3 contract returns the address of the best liquidity pool for the trade.
4. **PancakeRouter03:** The PancakeRouter03 contract calls the `swapExactTokensForTokens()` function on the liquidity pool contract.
5. **Liquidity pool contract:** The liquidity pool contract executes the trade and transfers the traded tokens to the recipient address.

Here is a more detailed explanation of each step:

**Step 1: User**

The user calls the `swapExactTokensForTokens()` function on the PancakeRouter03 contract. To do this, the user needs to have a wallet that is compatible with the Binance Smart Chain and that contains the tokens that they want to sell.

**Step 2: PancakeRouter03**

The PancakeRouter03 contract interacts with the FactoryV3 contract to find the best liquidity pool for the trade. The FactoryV3 contract tracks all of the liquidity pools on the PancakeSwap DEX. When the PancakeRouter03 contract receives a request to swap tokens, it queries the FactoryV3 contract to find the best liquidity pool for the trade.

**Step 3: FactoryV3**

The FactoryV3 contract returns the address of the best liquidity pool for the trade. The best liquidity pool is the pool that offers the best price for the trade and that has enough liquidity to execute the trade.

**Step 4: PancakeRouter03**

The PancakeRouter03 contract calls the `swapExactTokensForTokens()` function on the liquidity pool contract. The `swapExactTokensForTokens()` function takes the following parameters:

* `amountIn`: The amount of tokens that the user wants to sell.
* `amountOutMin`: The minimum amount of tokens that the user wants to receive.
* `path`: An array of token addresses that the trade should take.
* `to`: The address of the recipient of the traded tokens.
* `deadline`: The deadline by which the trade must be executed.

**Step 5: Liquidity pool contract**

The liquidity pool contract executes the trade and transfers the traded tokens to the recipient address. The liquidity pool contract works by matching buyers and sellers of tokens. When the PancakeRouter03 contract calls the `swapExactTokensForTokens()` function, the liquidity pool contract will match the user's sell order with a buy order from another user. Once the trade has been matched, the liquidity pool contract will transfer the traded tokens to the recipient address.

This is a simplified trace of the code, but it should give you a basic understanding of how a swap on PancakeSwap works.
