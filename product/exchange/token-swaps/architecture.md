# Architecture

[https://github.com/pancakeswap/pancake-toolkit/tree/master/packages/pancake-uikit](https://github.com/pancakeswap/pancake-toolkit/tree/master/packages/pancake-uikit)\
\
[https://github.com/pancakeswap/pancake-toolkit](https://github.com/pancakeswap/pancake-toolkit)\
\


Here is a simplified architecture of the PancakeSwap smart contract project:

```
                                      +--------------+
                                      | PancakeSwap |
                                      +--------------+
                                           |
                                           |
                                  +-----------------------+
                                  |    FactoryV3          |
                                  +-----------------------+
                                           |
                                           |
                   +----------------------------+
                   |     PancakeRouter03        |
                   +----------------------------+
                            |
                            |
                    +-----------------+
                    | Liquidity Pool  |
                    +-----------------+
```

The PancakeSwap smart contract project is composed of three main components:

* **FactoryV3:** FactoryV3 is responsible for creating and managing liquidity pools.
* **PancakeRouter03:** PancakeRouter03 is the main entry point for interacting with the PancakeSwap DEX. It allows users to swap tokens, add and remove liquidity from pools, and stake CAKE tokens.
* **Liquidity pools:** Liquidity pools are collections of tokens that are locked in smart contracts. They allow users to trade tokens without having to find a counterparty.

**How it works**

When a user wants to swap tokens on PancakeSwap, they interact with the PancakeRouter03 contract. The PancakeRouter03 contract then interacts with the FactoryV3 contract to find the best liquidity pool for the trade. Once the best liquidity pool has been found, the PancakeRouter03 contract executes the trade and transfers the traded tokens to the user's wallet.

**Role of factory, routes, and liquidity pools**

* **FactoryV3:** FactoryV3 is responsible for creating and managing liquidity pools. It also provides liquidity data to the PancakeSwap website and app.
* **Routes:** Routes are a way to specify the path that a trade should take through the various liquidity pools on PancakeSwap. This gives users more control over their trades and allows them to optimize their trades for price, execution time, or slippage tolerance.
* **Liquidity pools:** Liquidity pools are essential for trading on PancakeSwap. They allow users to trade tokens without having to find a counterparty.

This is a simplified architecture of the PancakeSwap smart contract project. The actual architecture is more complex, but this should give you a basic understanding of how it works.
