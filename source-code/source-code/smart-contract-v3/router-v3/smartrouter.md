# SmartRouter

The `SmartRouter` contract serves as a decentralized router for executing various types of swaps and transactions related to PancakeSwap and stable assets. This contract is designed to provide users with the ability to interact with different versions of the PancakeSwap decentralized exchange (DEX), including V2 and V3, as well as perform stable asset swaps.

{% code title="SmartRouter.sol" overflow="wrap" fullWidth="true" %}
```solidity
// SPDX-License-Identifier: GPL-2.0-or-later
pragma solidity =0.7.6;
pragma abicoder v2;

import '@pancakeswap/v3-periphery/contracts/base/SelfPermit.sol';
import '@pancakeswap/v3-periphery/contracts/base/PeripheryImmutableState.sol';

import './interfaces/ISmartRouter.sol';
import './V2SwapRouter.sol';
import './V3SwapRouter.sol';
import './StableSwapRouter.sol';
import './base/ApproveAndCall.sol';
import './base/MulticallExtended.sol';

/// @title Pancake Smart Router
contract SmartRouter is ISmartRouter, V2SwapRouter, V3SwapRouter, StableSwapRouter, ApproveAndCall, MulticallExtended, SelfPermit {
    constructor(
        address _factoryV2,
        address _deployer,
        address _factoryV3,
        address _positionManager,
        address _stableFactory,
        address _stableInfo,
        address _WETH9
    ) ImmutableState(_factoryV2, _positionManager) PeripheryImmutableState(_deployer, _factoryV3, _WETH9) StableSwapRouter(_stableFactory, _stableInfo) {}
}
```
{% endcode %}

Here's a breakdown of the key features and components of the `SmartRouter` contract:

1. **License Identifier**:
   * SPDX-License-Identifier: GPL-2.0-or-later: This line specifies the license under which the contract's source code is made available. In this case, it's the GNU General Public License version 2.0 or later.
2. **Solidity Pragma**:
   * pragma solidity =0.7.6: This line specifies the version of the Solidity programming language that should be used to compile the contract.
3. **ABICoder Version**:
   * pragma abicoder v2: This pragma indicates the use of ABICoder version 2, which is used to encode and decode function arguments and return values more efficiently.
4. **Imports**:
   * The contract imports various other contracts and interfaces needed for its functionality, including contracts related to PancakeSwap, stable assets, and utility contracts.
5. **Contract Inheritance**:
   * The `SmartRouter` contract inherits from multiple other contracts:
     * `ISmartRouter`: An interface that likely defines the functions and behaviors expected from this router contract.
     * `V2SwapRouter`: Contains functions and logic related to PancakeSwap V2.
     * `V3SwapRouter`: Contains functions and logic related to PancakeSwap V3.
     * `StableSwapRouter`: Contains functions and logic related to stable asset swaps.
     * `ApproveAndCall`: Provides functionality for approving and calling external contracts.
     * `MulticallExtended`: Allows for batch calling of multiple functions in a single transaction.
     * `SelfPermit`: A contract that likely provides self-permit functionality for interacting with the PancakeSwap contracts.
6. **Constructor**:
   * The constructor of the `SmartRouter` contract takes several addresses as arguments, including addresses related to PancakeSwap V2 and V3, stable asset information, and the Wrapped Ether (WETH) contract. These addresses are used to initialize the contract's state variables.

The Smart Router is built on top of three other contracts:

* V2SwapRouter: This contract implements the basic swapping algorithms for the PancakeSwap v2 AMM.
* V3SwapRouter: This contract implements the more advanced swapping algorithms for the PancakeSwap v3 AMM.
* StableSwapRouter: This contract implements the swapping algorithms for the PancakeSwap StableSwap pools.

In addition to these three contracts, the Smart Router also implements the following functionality:

* Approval and calling: This allows users to approve and call contracts in a single transaction.
* Multicall: This allows users to call multiple contracts in a single transaction.
* Self-permit: This allows users to approve contracts to spend their tokens without having to sign a transaction.



In summary, the `SmartRouter` contract is a comprehensive router that combines functionalities from different versions of PancakeSwap and stable asset swaps. Users can interact with this contract to execute swaps and other transactions on the PancakeSwap DEX and stable asset pools. The contract's design is modular, allowing it to integrate with different versions of PancakeSwap and other related protocols, making it a versatile tool for decentralized trading and asset management.
