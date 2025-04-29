# FractionalRE: Blockchain-based Fractional Real Estate Investment Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Clarity: 2.0](https://img.shields.io/badge/Clarity-2.0-blue.svg)](https://clarity-lang.org/)

## Overview

FractionalRE is a decentralized application (dApp) built on the Stacks blockchain that enables fractional real estate investment through tokenization. The platform allows property owners to register real estate assets, divide ownership into shares, and offer them to investors, democratizing access to real estate investment opportunities.

## Features

- **Property Tokenization**: Property owners can register assets and divide them into shares
- **Fractional Investment**: Investors can purchase shares of properties with STX tokens
- **Share Management**: Buy and sell shares with transparent pricing
- **Dividend Distribution**: Property income can be distributed proportionally to shareholders
- **Full Transparency**: All transactions are recorded on the Stacks blockchain

## Smart Contract Architecture

The core of FractionalRE is a Clarity smart contract that handles:

1. **Property Registration**: Creates tokenized representations of real-world properties
2. **Share Management**: Tracks share ownership across all investors
3. **Transaction Processing**: Handles STX transfers for purchases, sales, and dividends
4. **Event Logging**: Records all significant actions on the blockchain

## Technical Implementation

### Data Structure

- `properties`: Map storing property details (owner, value, shares, pricing)
- `investors`: Map tracking investment positions (property-wallet-shares relationship)
- Event logging system for tracking all platform activities

### Key Functions

- `register-property`: Creates a new tokenized property asset
- `buy-shares`: Allows investors to purchase property shares
- `sell-shares`: Enables shareholders to sell their positions
- `distribute-dividend`: Distributes rental income to shareholders

## Security Features

The contract includes several security measures:

- Input validation to prevent invalid data usage
- Balance checks to prevent unauthorized transactions
- Ownership verification for administrative functions
- Proper error handling with descriptive error codes

## Getting Started

### Prerequisites

- [Clarinet](https://github.com/hirosystems/clarinet) for local development and testing
- [Stacks Wallet](https://www.hiro.so/wallet) for deploying to testnet/mainnet

### Local Development

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/fractionalre.git
   cd fractionalre
   ```

2. Install Clarinet:
   ```bash
   curl -sSL https://curl.clarinet.sh | sh
   ```

3. Initialize the Clarinet project:
   ```bash
   clarinet new
   ```

4. Copy the contract to the contracts directory:
   ```bash
   cp src/fractionalre.clar contracts/
   ```

5. Test the contract:
   ```bash
   clarinet test
   ```

### Deployment

#### Testnet Deployment

1. Configure your Stacks wallet with testnet STX
2. Deploy using Clarinet:
   ```bash
   clarinet deploy --testnet
   ```

#### Mainnet Deployment

1. Ensure thorough testing and auditing before mainnet deployment
2. Deploy using Clarinet:
   ```bash
   clarinet deploy --mainnet
   ```

## Usage Examples

### Registering a Property

```clarity
(contract-call? .fractionalre register-property u1000000 u1000 u1000)
```
This registers a property valued at 1,000,000 STX with 1,000 shares at 1,000 STX per share.

### Buying Shares

```clarity
(contract-call? .fractionalre buy-shares u1 u5)
```
This purchases 5 shares of property #1.

### Selling Shares

```clarity
(contract-call? .fractionalre sell-shares u1 u2)
```
This sells 2 shares of property #1.

### Distributing Dividends

```clarity
(contract-call? .fractionalre distribute-dividend u1 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM u10000)
```
This distributes 10,000 STX in rental income to the specified investor for property #1.

## Roadmap

- **Q2 2025**: Add property valuation oracles
- **Q3 2025**: Implement secondary market for shares
- **Q4 2025**: Develop governance mechanisms for property management
- **Q1 2026**: Launch property-backed NFTs as certificates of ownership

## Contributing

We welcome contributions to FractionalRE! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The Stacks Foundation for blockchain infrastructure
- Clarity language documentation and community
- Real estate tokenization pioneers