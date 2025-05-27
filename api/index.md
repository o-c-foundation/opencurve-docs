---
layout: default
title: API Reference
nav_order: 8
has_children: true
permalink: /api
---

# OpenCurve API Reference

This section provides comprehensive documentation for the OpenCurve API endpoints. These APIs allow developers to interact with the OpenCurve platform programmatically, enabling custom integrations and applications.

## Authentication

All API requests require authentication using an API key. To obtain an API key:

1. Log in to your OpenCurve account
2. Navigate to Profile > API Keys
3. Generate a new API key
4. Use this key in all API requests in the `Authorization` header

Example:
```
Authorization: Bearer YOUR_API_KEY
```

## Base URL

All API requests should be made to:

```
https://api.opencurve.fun/v1
```

## Response Format

All responses are returned in JSON format. A typical response structure includes:

```json
{
  "success": true,
  "data": {
    // Response data here
  },
  "meta": {
    // Pagination information, etc.
  }
}
```

Error responses follow this structure:

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable error message"
  }
}
```

## Rate Limiting

API requests are rate-limited to 100 requests per minute per API key. If you exceed this limit, you'll receive a 429 Too Many Requests response.

The following headers are included in all responses to help manage rate limiting:

- `X-RateLimit-Limit`: Maximum number of requests allowed per minute
- `X-RateLimit-Remaining`: Number of requests remaining in the current window
- `X-RateLimit-Reset`: Time when the rate limit will reset (Unix timestamp)

## Available Endpoints

Browse the sidebar to explore all available API endpoints, organized by resource type:

- [Tokens](./tokens.html) - Endpoints for retrieving token information
- [Trading](./trading.html) - Endpoints for trading data and market information
- [Agents](./agents.html) - Endpoints for interacting with AI agents
- [Users](./users.html) - Endpoints for user account information
- [Blockchain](./blockchain.html) - Endpoints for blockchain integration

## SDKs and Libraries

We provide official SDKs for various programming languages to simplify API integration:

- [JavaScript/TypeScript](https://github.com/opencurve/opencurve-js)
- [Python](https://github.com/opencurve/opencurve-python)
- [PHP](https://github.com/opencurve/opencurve-php)

## Webhooks

OpenCurve also supports webhooks for real-time event notifications. See the [Webhooks](./webhooks.html) section for details on configuring and using webhooks.
