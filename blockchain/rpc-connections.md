---
layout: default
title: RPC Connections
parent: Blockchain
nav_order: 1
---

# RPC Connections in OpenCurve

This guide explains how OpenCurve manages blockchain Remote Procedure Call (RPC) connections and how to configure them for optimal performance.

## Understanding RPC Connections

RPC (Remote Procedure Call) connections are the primary way that decentralized applications like OpenCurve interact with blockchain networks. They allow the application to:

- Read blockchain data (balances, token information, contract state)
- Submit transactions (trades, token launches, approvals)
- Listen for events (trade completions, token transfers)

## OpenCurve's RPC Architecture

OpenCurve uses a multi-provider RPC approach for maximum reliability:

1. **Primary Providers**: Ankr and Infura
2. **Fallback Provider**: WalletConnect (requires valid Project ID)
3. **Failover System**: Automatic switching if a provider fails

## Supported RPC Providers

### Ankr

- **Endpoint Format**: `https://rpc.ankr.com/eth_sepolia/${ANKR_KEY}`
- **Configuration**: Add your Ankr API key to the `.env` file
- **Benefits**: High reliability and performance

### Infura

- **Endpoint Format**: `https://sepolia.infura.io/v3/${INFURA_KEY}`
- **Configuration**: Add your Infura API key to the `.env` file
- **Benefits**: Excellent documentation and support

### WalletConnect

- **Endpoint Format**: Uses WalletConnect's internal RPC with your Project ID
- **Configuration**: Requires a valid WalletConnect Project ID
- **Note**: Used primarily as a fallback when other providers fail

## Configuring RPC Connections

### Environment Variables

OpenCurve uses the following environment variables for RPC configuration:

```bash
# RPC Provider Keys
ANKR_KEY=your_ankr_key_here
INFURA_KEY=your_infura_key_here
PROJECT_ID=your_walletconnect_project_id_here

# Optional: Provider Preferences
PREFERRED_RPC_PROVIDER=ankr  # Options: ankr, infura, walletconnect
```

### Obtaining API Keys

#### Ankr API Key

1. Create an account at [Ankr](https://www.ankr.com/)
2. Navigate to the API Keys section
3. Create a new API key
4. Copy the key to your `.env` file

#### Infura API Key

1. Create an account at [Infura](https://infura.io/)
2. Create a new project
3. Copy the project ID (API key)
4. Add the key to your `.env` file

#### WalletConnect Project ID

1. Visit [WalletConnect Cloud](https://cloud.walletconnect.com/)
2. Create a new project
3. Copy the project ID
4. Add the ID to your `.env` file

## Troubleshooting RPC Issues

### Common Error Messages

#### 401 Unauthorized

- **Cause**: Missing or invalid API key
- **Solution**: Check that your API keys are correctly set in the `.env` file

#### Request Timeout

- **Cause**: RPC provider is experiencing high load or outages
- **Solution**: The application should automatically fail over to another provider

#### Rate Limit Exceeded

- **Cause**: Too many requests to the RPC provider
- **Solution**: Upgrade to a higher tier plan or distribute requests across providers

### Advanced Troubleshooting

If you're experiencing persistent RPC connection issues:

1. **Check Browser Console**: Look for specific error messages
2. **Verify Network Status**: Check provider status pages for outages
3. **Clear Application Cache**: This refreshes the RPC connection settings
4. **Update RPC Settings**: Update your API keys and restart the application
5. **Try Alternative Providers**: If one provider is having issues, manually switch to another

## RPC Performance Optimization

For best performance with OpenCurve:

1. **Use Geographically Close Endpoints**: Choose RPC endpoints in your region
2. **Implement Request Batching**: Group multiple requests when possible
3. **Enable Caching**: Cache frequently accessed blockchain data
4. **Monitor Usage**: Keep track of your RPC usage to avoid rate limits
5. **Use Multiple Providers**: Distribute requests across different providers

## Security Considerations

When working with RPC connections:

1. **Never expose API keys**: Keep keys in `.env` files and never commit them to public repositories
2. **Use HTTPS endpoints**: Always use encrypted connections
3. **Implement rate limiting**: Prevent abuse of your RPC connections
4. **Monitor for unusual activity**: Watch for unexpected request patterns
5. **Regularly rotate API keys**: Change keys periodically for better security

## Next Steps

- [Blockchain Transaction Management](./transactions.html)
- [Smart Contract Interactions](./smart-contracts.html)
- [Gas Optimization Techniques](./gas-optimization.html)
