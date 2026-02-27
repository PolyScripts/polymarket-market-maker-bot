# Polymarket Market Maker Bot | Automated CLOB Keeper for Passive Trading Income

**Language / 语言:** [English](README.md) | [中文](README.zh-CN.md)

> **Contact:** [Telegram @movez_x](https://t.me/movez_x)

---

## What Is This Bot?

The **Polymarket Market Maker Bot** is an automated keeper that provides liquidity on the [Polymarket](https://polymarket.com) CLOB (Central Limit Order Book). It continuously places and cancels orders around the midpoint price, acting as a market maker to earn the bid-ask spread while helping other traders execute their trades.

Whether you're a prediction market enthusiast or a DeFi trader looking for passive income, this bot runs 24/7 to capture market-making profits on Polymarket.

---

## 5 Advantages for Traders

| # | Advantage | Why It Matters |
|---|-----------|----------------|
| 1 | **Passive Income** | Earn the bid-ask spread automatically. Your capital works for you while you sleep—no manual trading required. |
| 2 | **24/7 Automated Trading** | The bot monitors the order book and rebalances orders every 30 seconds (configurable). No need to watch charts or place orders manually. |
| 3 | **Two Professional Strategies** | Choose **AMM** (concentrated liquidity style) or **Bands** (multi-tier order placement). Each strategy has tunable parameters for your risk/reward profile. |
| 4 | **Full Control & Transparency** | Open-source code, configurable spreads, depth, and collateral limits. You decide how much capital to deploy and how tight your quotes are. |
| 5 | **Graceful Shutdown** | On exit (SIGTERM), the bot cancels all open orders and exits cleanly—no orphaned orders left on the book. |

---

## Get Full Code, Custom Features, Help, or Premium

- **Full source code** – This repository contains the core bot. For extended features or custom builds, reach out.
- **Add features** – Need a new strategy, multi-market support, or integrations? We can help.
- **Technical support** – Stuck on setup or configuration? Get help from the team.
- **Premium version** – For advanced features, dedicated support, or managed deployment.

**Contact via Telegram:** [@movez_x](https://t.me/movez_x)

---

## Quick Start – Run the Bot

### Requirements

- Python 3.10
- A Polymarket account with USDC (Polygon)
- A condition ID for the market you want to make

### 1. Install

```bash
./install.sh
```

This creates a virtual environment and installs dependencies.

### 2. Configure Environment

Create a `.env` file (see `.env.example`):

```
PRIVATE_KEY=your_private_key
RPC_URL=https://polygon-rpc.com
CLOB_API_URL=https://clob.polymarket.com
```

### 3. Configure Market & Strategy

Edit `config.env`:

```
CONDITION_ID=0x...   # Hex condition ID of your Polymarket market
STRATEGY=amm         # or "bands"
CONFIG=./config/amm.json   # or ./config/bands.json
```

Adjust strategy parameters in `./config/amm.json` or `./config/bands.json` as needed.

### 4. Run

```bash
./run-local.sh
```

### Docker (Alternative)

```bash
docker compose up
```

---

## Strategy Overview

| Strategy | Description |
|----------|-------------|
| **AMM** | Concentrated liquidity style—places orders at multiple price levels with configurable spread, delta, and depth. See [docs/strategies/amm.md](docs/strategies/amm.md). |
| **Bands** | Multi-band strategy—maintains orders within specified price bands and size ranges. See [docs/strategies/bands.md](docs/strategies/bands.md). |

The bot syncs every 30 seconds by default: it fetches the midpoint, computes expected orders, cancels outdated ones, and places new ones.

---

## Disclaimer

This software is experimental and in active development. Use at your own risk. Always test with small amounts first.

---

## Contact

**Telegram:** [@movez_x](https://t.me/movez_x)

---

## 中文版 | Chinese Version

[查看中文说明 → README.zh-CN.md](README.zh-CN.md)
