# Vektora Auto-Trade Bot

Auto-trades Binance Futures based on [Vektora](https://vektora.trade) signals, 24/7.

## Deploy to Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.com/deploy/vektora-bot-template?referralCode=rWoFxF)

## Setup

1. Subscribe at [vektora.trade](https://vektora.trade) to get your Signal API key
2. Create a Binance Futures API key
3. Click the deploy button above
4. Set these 3 variables in Railway:

| Variable | Description |
|----------|-------------|
| `SIGNAL_API_KEY` | Your Vektora API key (from subscription email) |
| `BINANCE_APIKEY` | Binance Futures API key |
| `BINANCE_SECRET` | Binance Futures API secret |

5. Deploy — the bot auto-configures and starts trading

## Dashboard Controls

Once deployed, manage your bot from [vektora.trade/dashboard](https://vektora.trade/dashboard):

- **Max Positions** — choose 1-18 (default 5, recommended)
- **AI Trader** — toggle AI-powered entry filtering and exit management
- **Profit Lock** — toggle automatic profit-locking on pullbacks

Changes apply to your bot within 30 seconds.

## Optional: Telegram Alerts

Add these variables to get trade notifications on Telegram:

| Variable | Description |
|----------|-------------|
| `TELEGRAM_BOT_TOKEN` | Create a bot via [@BotFather](https://t.me/BotFather) |
| `TELEGRAM_CHAT_ID` | Get your ID from [@userinfobot](https://t.me/userinfobot) |

## How It Works

- Connects to Vektora signal server automatically
- Receives direction-flip signals for 18 crypto futures pairs
- Executes trades on your Binance account
- 5% risk per trade, 10x leverage, 8% stop-loss on every position
- Reports status to dashboard every scan cycle
- Polls for commands (pause, resume, max positions) from dashboard
- Runs 24/7 on Railway — auto-reconnects if disconnected

## Security

- Your Binance API keys stay on YOUR Railway instance
- Keys are never stored on Vektora servers
- Trades execute through an isolated proxy with IP whitelisting
- The proxy signs requests in memory — never stores credentials

## Full Setup Guide

[vektora.trade/guide](https://vektora.trade/guide) — step-by-step with Binance account setup, API key creation, and troubleshooting.

## Support

- Email: support@vektora.trade
- Telegram: [@donchian_alert_bot](https://t.me/donchian_alert_bot)
