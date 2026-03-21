# Vektora Trading Bot

Auto-trades Binance Futures based on [Vektora](https://vektora.trade) signal server.

## Deploy to Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/71c12d88-cf6d-4ad0-b0d3-6c2f0b8b75ef)

## How It Works

1. Subscribe at [vektora.trade](https://vektora.trade) to get your Signal API key
2. Deploy this bot on Railway (one click above)
3. Configure via the `/api/configure` endpoint with your keys
4. Bot connects to Vektora signal server, receives trading signals, and auto-executes on Binance Futures

## Configuration

After deploying, configure your bot:

```bash
curl -X POST https://YOUR-BOT-URL/api/configure \
  -H "Content-Type: application/json" \
  -d '{
    "setup_token": "your-chosen-token",
    "binance_api_key": "...",
    "binance_secret": "...",
    "signal_api_key": "issued-by-vektora"
  }'
```

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `PROXY_KEY` | Yes | Provided after subscription |
| `SIGNAL_SERVER_URL` | No | Default: Vektora production server |
| `PROXY_URL` | No | Default: Vektora Binance proxy |

## Endpoints

- `GET /health` — Bot status (no auth)
- `POST /api/configure` — Set credentials (first call sets token)
- `GET /api/status` — Positions and P&L (requires token)

## Security

- Your Binance API keys are stored locally on YOUR Railway instance
- Keys are never sent to Vektora — trades execute through an isolated proxy
- The proxy only signs requests; it never stores credentials
