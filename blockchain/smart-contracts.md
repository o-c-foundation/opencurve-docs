---
layout: default
title: Smart Contracts
parent: Blockchain
nav_order: 2
---

# OpenCurve Smart Contracts

This page provides an overview of the smart contracts that power the OpenCurve platform.

## Core Contracts

### Token Factory

The Token Factory contract is responsible for creating new tokens on the OpenCurve platform.

- **Functionality**: Creates ERC-20 token contracts with predefined parameters
- **Key Features**:
  - Standardized token creation with security checks
  - Automatic liquidity locking
  - Ownership renunciation
  - Agent integration hooks
- **Address**: *varies by network*

### Launchpad Registry

The Launchpad Registry maintains a list of all tokens created through the platform.

- **Functionality**: Tracks token deployments and metadata
- **Key Features**:
  - Token registration and verification
  - Metadata storage (name, symbol, logo)
  - Creator information
  - Agent associations
- **Address**: *varies by network*

### Liquidity Locker

The Liquidity Locker secures trading pair liquidity to prevent rug pulls.

- **Functionality**: Locks liquidity provider tokens for a specified period
- **Key Features**:
  - Permanent locking option
  - Time-based locking schedules
  - Owner verification
  - Lock status verification
- **Address**: *varies by network*

### Agent Registry

The Agent Registry manages the connection between tokens and AI agents.

- **Functionality**: Links tokens to agent services and capabilities
- **Key Features**:
  - Agent registration and verification
  - Capability definitions
  - Access control
  - Usage tracking
- **Address**: *varies by network*

## Token Contract

Each token created on OpenCurve has its own ERC-20 contract with these characteristics:

### Standard Functions

- `name()`: Returns the token name
- `symbol()`: Returns the token symbol
- `decimals()`: Returns the number of decimals (typically 18)
- `totalSupply()`: Returns the total token supply
- `balanceOf(address)`: Returns the token balance of an address
- `transfer(address, amount)`: Transfers tokens to an address
- `approve(address, amount)`: Approves an address to spend tokens
- `transferFrom(address, address, amount)`: Transfers tokens between addresses
- `allowance(address, address)`: Returns the approved spending amount

### OpenCurve Extensions

- `owner()`: Returns the contract owner (typically renounced after creation)
- `renounceOwnership()`: Permanently renounces ownership
- `getAgentInfo()`: Returns information about associated agents
- `getLockInfo()`: Returns liquidity locking information

## Contract Security

OpenCurve's smart contracts incorporate several security features:

1. **Ownership Renunciation**: Token contracts have their ownership renounced after creation
2. **Permanent Liquidity Locks**: Initial liquidity is locked permanently
3. **Standardized Code**: All contracts use audited, standardized code
4. **No Mint Functions**: Tokens have fixed supply with no ability to mint more
5. **No Special Privileges**: No backdoors or special privileges for any party

## Audits

OpenCurve smart contracts have undergone security audits by reputable firms:

- **Token Factory**: Audited by [Security Firm]
- **Liquidity Locker**: Audited by [Security Firm]
- **Standard Token Contract**: Audited by [Security Firm]

Audit reports are available on request.

## Contract Addresses

| Contract | Ethereum Mainnet | Sepolia Testnet |
|----------|-----------------|-----------------|
| Token Factory | 0x... | 0x... |
| Launchpad Registry | 0x... | 0x... |
| Liquidity Locker | 0x... | 0x... |
| Agent Registry | 0x... | 0x... |

## For Developers

If you're a developer looking to interact with OpenCurve contracts:

1. [Contract ABIs](./contract-abis.html) - Interface definitions for all contracts
2. [Integration Guide](./integration.html) - How to integrate with OpenCurve
3. [Security Best Practices](./security.html) - Security considerations when interacting with contracts
