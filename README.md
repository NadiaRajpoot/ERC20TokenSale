# ERC20TokenSale

A decentralized ERC20 token sale smart contract that allows users to buy tokens with Ether. This contract provides secure token transfers, price-based calculations, and refunds for excess payments, ensuring a seamless and transparent token sale process on the Ethereum blockchain.

## Features

- **Token Sale:** Enables users to purchase tokens using Ether at a fixed price.
- **Secure Transactions:** Implements OpenZeppelin standards for secure token transfers.
- **Refund Mechanism:** Automatically refunds excess Ether sent during the transaction.
- **Flexibility:** Supports ERC20 tokens with customizable decimals.
- **Transparency:** Emits events for key transactions to ensure traceability.

## Contracts

### ERC20Token
The ERC20 token contract implementing the following functionalities:
- Minting tokens for distribution.
- Burning tokens as needed.
- Role-based access control for administrative actions.

### TokenSale
The token sale contract enables users to purchase tokens directly:
- Calculates token amounts based on the Ether sent.
- Transfers purchased tokens to the buyer's address.
- Refunds excess Ether automatically.

## Deployment Instructions

1. **Deploy ERC20Token Contract**
   - Deploy the `ERC20Token` contract on the Ethereum network.
   - Assign roles (e.g., MINTER_ROLE) to authorized addresses.

2. **Deploy TokenSale Contract**
   - Deploy the `TokenSale` contract, passing the `ERC20Token` contract address as a parameter.

3. **Approve TokenSale Contract**
   - Use the `approve` function of `ERC20Token` to allow the `TokenSale` contract to transfer tokens on your behalf.

## Usage

### Minting Tokens
```solidity
// Mint 100 tokens (with decimals considered)
ERC20Token.mint(0xRecipientAddress, 100 * 10 ** decimals);
