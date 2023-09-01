# Ethscriptions Escrower Smart Contract

The Ethscriptions Escrower is a smart contract designed to manage the transfer of Ethscriptions (Ethereum-based subscriptions) between users while enforcing a cooldown period between transfers. It uses Rubidity, a language for writing secure Ethereum smart contracts.

## Overview

- **Smart Contract Name**: EthscriptionsEscrower
- **Current Version**: 1.0.0
- **License**: MIT License
- **Author**: Gooseverse.eth

## Features

- Transfer Ethscriptions between users.
- Enforce a cooldown period for Ethscription transfers.
- Track the receipt of potential Ethscriptions.
- Secure and efficient storage with Rubidity.
- Built following best practices for secure contract development.

## Getting Started

1. Clone the repository to your local machine:

```shell
git clone [repository-url]

1)Compile the Rubidity contract using a Rubidity compiler. Ensure you have the necessary dependencies installed.
2)Deploy the compiled contract to the Ethereum blockchain.
3)Interact with the contract using Ethereum wallets or smart contract interfaces.

Usage

Transfer Ethscriptions
Use the _transferEthscription function to transfer an Ethscription from the previousOwner to the to address. This function enforces a cooldown period to prevent rapid transfers.

_transferEthscription(previousOwner: Address, to: Address, ethscriptionId: Bytes32)

Withdraw Ethscription
The withdrawEthscription function allows users to withdraw Ethscriptions from their own address. It invokes the _transferEthscription function to initiate the withdrawal.
withdrawEthscription(ethscriptionId: Bytes32)

Deposit Potential Ethscription
The _onPotentialEthscriptionDeposit function is called when a user deposits a potential Ethscription. It validates the deposit and tracks it for future transfers.

_onPotentialEthscriptionDeposit(previousOwner: Address, userCalldata: Bytes)
Check Remaining Cooldown Blocks
Use the blocksRemainingUntilValidTransfer function to check the remaining cooldown blocks for a particular Ethscription transfer.
blocksRemainingUntilValidTransfer(previousOwner: Address, ethscriptionId: Bytes32): Uint256
Error Handling

The contract defines several custom errors to handle exceptional cases such as invalid Ethscription length, attempts to transfer nonexistent Ethscriptions, and more.

License

This contract is released under the MIT License. You are free to use, modify, and distribute it as per the terms of the license.

Acknowledgments

Special thanks to the Rubidity community for their work on this secure contract language.
