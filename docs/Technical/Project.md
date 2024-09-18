---
title: Technical Documentation
sidebar_label: Technical Overview
---

# Technical Documentation

## Overview
Arcane Wallet, developed by **Faez Labs**, is a secure and user-friendly multi-chain crypto wallet that supports **Ethereum** and **CrossFi** blockchains. It allows users to perform transactions, manage assets, and swap tokens across chains using a custom **Automated Market Maker (AMM) protocol**. This technical document outlines the architecture, supported features, and the underlying technologies used in Arcane Wallet.

## Architecture
### Frontend
- **Framework**: The frontend of Arcane Wallet is built using **React.js** for a modern, responsive user interface.

### Backend
- **Backend Service**: Our backend service is lightweight, as most of the wallet's logic is handled on the frontend. However, backend services are used for maintaining connectivity to blockchain nodes and handling the cross-chain swapping logic. Allowing the interconnection between the two blockchains.
- **Blockchain Communication**: We use **Web3.js** and **Ethers.js** libraries for interacting with Ethereum, while **Cosmos SDK** integration is planned for CrossFi. Blockchain data is fetched directly from RPC nodes.
  
### APIs
Arcane Wallet integrates directly with blockchain APIs to facilitate real-time transactions and data handling.
- **Ethereum API**: We use standard Ethereum APIs, accessed via Web3.js or Ethers.js, for executing transactions, interacting with smart contracts, and querying account balances.
- **CrossFi API**: Planned for future integration, the [CrossFi API](https://docs.crossfi.org/crossfi-chain/reference/api-and-available-endpoints) will be used for managing accounts, transactions, and smart contract interaction on the CrossFi blockchain.

## Supported Chains
### Ethereum Chain
- Full support for transaction handling, token transfers, and interacting with Ethereum smart contracts.
- **AMM Protocol**: Fully functional cross-chain token swapping using our custom AMM protocol, leveraging Ethereum's liquidity pools.

### CrossFi Chain (Upcoming)
- **EVM-Compatible**: CrossFi's support for Ethereum Virtual Machine (EVM) means that our smart contracts and AMM protocol can be deployed with minimal changes. We faced some problems to test this as we we're low on tokens to test the functionality. 
- **API Integration**: Once fully integrated, CrossFi chain will allow the same seamless experience currently available on Ethereum.

## Cross-Chain Protocol
### Cross-Chain Token Swapping
Arcane Wallet enables **cross-chain token swapping** using a custom **Automated Market Maker (AMM) protocol**. Here’s how it works:

- **Liquidity Pools**: Our AMM protocol uses liquidity pools to provide seamless token swaps with minimal slippage. Liquidity pools are currently supported on Ethereum and Solana for now. As we are allowing tokens swappping between Ethereum and Solana. CrossFi integration will require to deploy the current structure only into the chain.
- **Swapping Process**: When a user initiates a token swap, our AMM automatically calculates the optimal token amounts and routes the transaction through available liquidity pools.
- **Cross-Chain Functionality**: In future updates, the AMM will enable cross-chain swaps between Ethereum and CrossFi, CrossFi and Solana, and many more.

### Example Flow
1. User selects the token they wish to swap on Ethereum(know only available **LINK** to **SOL**).
2. The AMM calculates the optimal swap route and finds the liquidity pool with the best rate.
3. The transaction is signed using the user’s private key and broadcast to the Ethereum network.
4. Once confirmed, the swapped tokens appear in the user’s wallet.
5. In the future, if CrossFi is involved, the AMM will manage the bridging of assets between chains.

## Transaction Flow
### Swapping Transaction Flow
1. **Initiation**: User creates a transaction or initiates a token swap.
2. **Signing**: The transaction is signed locally using the private key stored securely in the browser or mobile device.
3. **Broadcast**: The signed transaction is broadcast to the Ethereum network via the connected RPC node.
4. **Confirmation**: The bridge listens for transaction confirmations and sends the swapped tokens back to the user’s wallet on the other chain.

## Token Swapping Mechanism
### AMM Protocol
Arcane Wallet’s **Automated Market Maker (AMM) protocol** allows for efficient token swaps on Ethereum, and eventually CrossFi, with the following characteristics:

- **Liquidity Optimization**: The AMM protocol finds the best liquidity pools for token swaps, minimizing slippage.
- **Slippage Protection**: Built-in slippage control prevents users from losing value due to high market volatility.
- **Future Plans**: We will extend AMM functionality to CrossFi once EVM support is fully implemented.

## Security & Encryption
Security is a core priority in Arcane Wallet. Below are key security features we’ve implemented:

- **Private Key Management**: Private keys are securely stored locally with encryption, in the browser’s local storage (for web users).
- **Encryption**: All private keys are encrypted with **AES-256** encryption, ensuring they cannot be accessed without user authentication.
- **Transaction Signing**: Transactions are signed locally before being broadcast to the blockchain, ensuring that the private key is never exposed.
- **Audits**: We plan regular security audits to ensure that our wallet is resilient against potential attacks and vulnerabilities.

## Smart Contract Implementation
### Ethereum Smart Contracts
We have deployed custom smart contracts on Ethereum to handle:
- **Token Swapping**: Our AMM contracts manage token swaps by interacting with liquidity pools.
- **Cross-Chain Interaction**: Future updates will introduce contracts that handle cross-chain token bridges between Ethereum and CrossFi.

### CrossFi Smart Contracts (Future)
CrossFi's EVM compatibility makes it straightforward to deploy Ethereum-compatible smart contracts on CrossFi. This will allow us to extend the AMM protocol and cross-chain swaps seamlessly to the CrossFi ecosystem.

## User Authentication & Wallet Management
Arcane Wallet handles user authentication using local storage and secure key management. Here’s how the wallet manages keys and authenticates users:
- **Local Key Storage**: Private keys are stored securely on the user's device, never leaving the local environment.
- **Authentication**: Users unlock their wallets with a password, which decrypts their private key for signing transactions.
- **Secure Signing**: All transactions are signed locally, ensuring that private keys are never exposed to third-party servers.

## Gas Fees Optimization
Arcane Wallet optimizes gas fees in Ethereum by:
- **Real-Time Gas Price Monitoring**: The wallet fetches real-time gas prices and recommends the most optimal price for users.
- **CrossFi Fees**: For future CrossFi support, we will integrate a similar fee optimization mechanism, leveraging its low-fee structure.

## Development Roadmap
### Current Features
- Full Ethereum support: Transactions, token transfers, and AMM-based token swaps.
- Secure key management and transaction signing.
  
### Upcoming Features
- **CrossFi Chain Integration**: EVM-based transactions and AMM integration with CrossFi chain.
- **Multi-Chain Expansion**: Support for additional blockchains beyond Ethereum and CrossFi.
- **Enhanced Features**: Staking, NFTs, governance tokens, and more.
- **Compatibility with websites**: Integration with websites to allow users to interact with the wallet directly from the website, and platforms can integrate It.

## Conclusion
Arcane Wallet, built by Faez Labs, offers a scalable, secure, and user-friendly solution for cross-chain crypto management. With support for Ethereum and planned integration for CrossFi, Arcane Wallet is poised to become a leading platform for seamless, multi-chain token management and swapping.

Stay tuned for future updates as we continue to improve and expand Arcane Wallet’s capabilities.
