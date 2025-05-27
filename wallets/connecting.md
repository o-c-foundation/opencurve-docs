---
layout: default
title: Connecting Your Wallet
parent: Wallets
nav_order: 1
---

# Connecting Your Wallet to OpenCurve

This guide explains how to connect your Web3 wallet to OpenCurve and troubleshoot common connection issues.

## Supported Wallets

OpenCurve supports a variety of Web3 wallets, including:

- **MetaMask** - Browser extension and mobile app
- **WalletConnect** - Connect any compatible mobile wallet
- **Coinbase Wallet** - Direct integration with Coinbase
- **Trust Wallet** - Mobile wallet with WalletConnect support
- **Ledger & Trezor** - Hardware wallets (via MetaMask or WalletConnect)

## Connection Methods

### MetaMask

1. Install the [MetaMask extension](https://metamask.io/download.html) for your browser
2. Create or import a wallet
3. Click "Connect Wallet" on OpenCurve
4. Select MetaMask from the options
5. Approve the connection request in the MetaMask popup

### WalletConnect

1. Click "Connect Wallet" on OpenCurve
2. Select WalletConnect
3. Scan the QR code with your mobile wallet
4. Approve the connection request in your wallet

### Coinbase Wallet

1. Install the [Coinbase Wallet extension](https://www.coinbase.com/wallet) or mobile app
2. Create or import a wallet
3. Click "Connect Wallet" on OpenCurve
4. Select Coinbase Wallet
5. Approve the connection request

## Supported Networks

OpenCurve currently supports the following networks:

| Network | Chain ID | Description |
|---------|----------|-------------|
| Ethereum Mainnet | 1 | Main Ethereum blockchain network |
| Sepolia Testnet | 11155111 | Ethereum test network for development |

## Configuring Your Wallet

### Adding Networks

If your wallet doesn't already have the required networks, you can add them:

#### Adding Sepolia to MetaMask

1. Open MetaMask and click the network dropdown
2. Select "Add Network"
3. Choose "Add a network manually"
4. Enter the following details:
   - Network Name: `Sepolia Test Network`
   - RPC URL: `https://rpc.ankr.com/eth_sepolia` or `https://sepolia.infura.io/v3/`
   - Chain ID: `11155111`
   - Currency Symbol: `SepoliaETH`
   - Block Explorer URL: `https://sepolia.etherscan.io`

### Getting Test ETH

For testing on Sepolia:

1. Visit a Sepolia faucet like [sepoliafaucet.com](https://sepoliafaucet.com/)
2. Enter your wallet address
3. Complete any verification steps
4. Receive test ETH to your wallet

## Troubleshooting Connection Issues

### RPC Connection Errors

If you experience RPC connection errors:

1. **Check Network Status**: Ensure the selected network is operational
2. **Switch RPC Providers**: Try using alternative RPC endpoints:
   - Ankr: `https://rpc.ankr.com/eth_sepolia/[YOUR_ANKR_KEY]`
   - Infura: `https://sepolia.infura.io/v3/[YOUR_INFURA_KEY]`
3. **Clear Browser Cache**: Clear your browser cache and cookies
4. **Update Wallet**: Ensure your wallet software is up to date
5. **Disable VPN**: Some VPNs may interfere with blockchain connections

### WalletConnect Issues

If experiencing issues with WalletConnect:

1. Ensure you have the latest version of your mobile wallet
2. Check that your wallet supports WalletConnect v2
3. Make sure your Project ID is correctly configured
4. Try reconnecting by clicking "Connect Wallet" again
5. If persistent issues occur, try using the QR code directly from [walletconnect.com](https://walletconnect.com/)

### Transaction Failures

If transactions fail:

1. **Insufficient Gas**: Ensure you have enough ETH for gas fees
2. **Gas Price Too Low**: Increase gas price during high network congestion
3. **Slippage Issues**: For trading, try increasing slippage tolerance
4. **Contract Approval**: Check if you need to approve token spending first

## Best Practices for Wallet Security

1. **Never Share Private Keys**: Keep your private keys and seed phrases secure
2. **Use Hardware Wallets**: For large holdings, consider a hardware wallet
3. **Check URLs**: Always verify you're on the official OpenCurve website
4. **Review Transactions**: Carefully check all transaction details before signing
5. **Create a Dedicated Wallet**: Consider using a separate wallet for DeFi activities

## Next Steps

- [Managing Multiple Wallets](./multiple-wallets.html)
- [Understanding Gas Fees](./gas-fees.html)
- [Wallet Security Guide](./security.html)
