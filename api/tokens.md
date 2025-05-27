---
layout: default
title: Token APIs
parent: API Reference
nav_order: 1
---

# Token APIs

The Token APIs provide access to information about tokens created and traded on the OpenCurve platform.

## Get All Tokens

Retrieves a list of all tokens on the platform.

```
GET /tokens
```

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `page` | integer | Page number for pagination |
| `per_page` | integer | Number of results per page (default: 25, max: 100) |
| `sort` | string | Field to sort by (options: created_at, name, volume, price) |
| `direction` | string | Sort direction (options: asc, desc) |
| `chain_id` | integer | Filter by blockchain network ID |
| `search` | string | Search query for token name or symbol |

### Response

```json
{
  "success": true,
  "data": [
    {
      "id": "123",
      "name": "OpenCurve Token",
      "symbol": "OCT",
      "description": "A utility token for the OpenCurve platform",
      "logo_url": "https://opencurve.fun/storage/logos/oct.png",
      "contract_address": "0x1234567890abcdef1234567890abcdef12345678",
      "chain_id": 11155111,
      "price_usd": 1.23,
      "market_cap": 1230000,
      "volume_24h": 45600,
      "price_change_24h": 5.4,
      "holders_count": 1234,
      "created_at": "2025-03-15T14:23:45Z"
    },
    // More tokens...
  ],
  "meta": {
    "current_page": 1,
    "last_page": 5,
    "per_page": 25,
    "total": 123
  }
}
```

## Get Token Details

Retrieves detailed information about a specific token.

```
GET /tokens/{token_id}
```

### Path Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `token_id` | string | The unique identifier of the token |

### Response

```json
{
  "success": true,
  "data": {
    "id": "123",
    "name": "OpenCurve Token",
    "symbol": "OCT",
    "description": "A utility token for the OpenCurve platform",
    "logo_url": "https://opencurve.fun/storage/logos/oct.png",
    "contract_address": "0x1234567890abcdef1234567890abcdef12345678",
    "chain_id": 11155111,
    "price_usd": 1.23,
    "market_cap": 1230000,
    "volume_24h": 45600,
    "price_change_24h": 5.4,
    "price_change_7d": 12.3,
    "holders_count": 1234,
    "total_supply": 1000000,
    "circulating_supply": 750000,
    "owner": {
      "id": "456",
      "username": "opencurve_creator"
    },
    "social_links": {
      "website": "https://opencurve.fun",
      "twitter": "https://twitter.com/opencurve",
      "telegram": "https://t.me/opencurve",
      "discord": "https://discord.gg/opencurve"
    },
    "agents": [
      {
        "id": "789",
        "name": "OCT Assistant",
        "description": "AI assistant for OpenCurve token holders",
        "type": "support"
      }
    ],
    "created_at": "2025-03-15T14:23:45Z"
  }
}
```

## Get Token Price History

Retrieves historical price data for a specific token.

```
GET /tokens/{token_id}/prices
```

### Path Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `token_id` | string | The unique identifier of the token |

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `interval` | string | Time interval for data points (options: 5m, 15m, 1h, 4h, 1d, 1w) |
| `from` | string | Start date in ISO 8601 format |
| `to` | string | End date in ISO 8601 format |

### Response

```json
{
  "success": true,
  "data": [
    {
      "timestamp": "2025-05-26T00:00:00Z",
      "price": 1.21,
      "volume": 12500
    },
    {
      "timestamp": "2025-05-27T00:00:00Z",
      "price": 1.23,
      "volume": 14300
    },
    // More data points...
  ]
}
```

## Get Token Holders

Retrieves a list of token holders for a specific token.

```
GET /tokens/{token_id}/holders
```

### Path Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `token_id` | string | The unique identifier of the token |

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `page` | integer | Page number for pagination |
| `per_page` | integer | Number of results per page (default: 25, max: 100) |

### Response

```json
{
  "success": true,
  "data": [
    {
      "address": "0xabcdef1234567890abcdef1234567890abcdef12",
      "balance": 125000,
      "percentage": 12.5
    },
    {
      "address": "0x0987654321fedcba0987654321fedcba09876543",
      "balance": 85000,
      "percentage": 8.5
    },
    // More holders...
  ],
  "meta": {
    "current_page": 1,
    "last_page": 3,
    "per_page": 25,
    "total": 68
  }
}
```

## Get Token Trades

Retrieves recent trades for a specific token.

```
GET /tokens/{token_id}/trades
```

### Path Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `token_id` | string | The unique identifier of the token |

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `page` | integer | Page number for pagination |
| `per_page` | integer | Number of results per page (default: 25, max: 100) |

### Response

```json
{
  "success": true,
  "data": [
    {
      "id": "t123",
      "transaction_hash": "0x1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef",
      "type": "buy",
      "amount": 500,
      "price": 1.23,
      "value_usd": 615,
      "buyer": "0xabcdef1234567890abcdef1234567890abcdef12",
      "seller": "0x0987654321fedcba0987654321fedcba09876543",
      "timestamp": "2025-05-27T09:45:23Z"
    },
    // More trades...
  ],
  "meta": {
    "current_page": 1,
    "last_page": 10,
    "per_page": 25,
    "total": 245
  }
}
```
