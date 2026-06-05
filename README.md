# Hyperliquid Live Trading Bot – Automated Strategies on Hyperliquid

**English** | [中文版 / Chinese](README_CN.md)

---

## What Is This?

A **Hyperliquid live trading bot** built in Python. It connects through **CCXT**, loads OHLCV data, runs a **technical-indicator strategy** (RSI example included), and can open or close perpetual positions with optional **take-profit** and **stop-loss**.

- **Hyperliquid via CCXT** – Wallet address + private key authentication
- **Example RSI strategy** – Long entry/exit rules you can replace or extend
- **Risk controls** – Position size as % of balance, leverage, isolated/cross margin, TP/SL percentages
- **Market orders** – Optional TP/SL attached when opening (see `HyperliquidClient.place_market_order`)
- **Easy to extend** – Add indicators in `compute_indicators()` using the `ta` library

---

## 5 Advantages for Traders

1. **Hands-off execution** – Run the script on a schedule; no manual order entry for each signal.
2. **Same stack as many bots** – CCXT + pandas + `ta`; familiar tooling and docs.
3. **Tunable risk** – Position %, leverage, margin mode, and TP/SL live in one `params` block.
4. **Strategy is yours** – Swap RSI rules or add MACD, Bollinger, etc., without changing the exchange layer.
5. **Transparent code** – Logic is plain Python; no hidden steps between indicator and order.

---

## Basic Live Bot

This repo is a **starter live-trading script** (`hyperliquid-trading-live-bot.py`). For full customization, support, or advanced features, see **Contact** below.

---

## How to Run

```bash
# 1. Set environment variables (e.g. in .env with python-dotenv)
#    HYPERLIQUID_WALLET_ADDRESS
#    HYPERLIQUID_PRIVATE_KEY

# 2. Install dependencies
pip install ccxt pandas ta python-dotenv

# 3. Edit strategy settings in hyperliquid-trading-live-bot.py (params, ignore_* flags)

# 4. Run (test on small size / testnet if available before mainnet)
python hyperliquid-trading-live-bot.py
```

**Security:** Never commit real keys. Use a dedicated trading wallet and limits you can afford to lose.

---

## Contact

**Telegram:** [@dexoryn](https://t.me/dexoryn)  
**Discord:** dexoryn_  
**X (Twitter):** [@Dexoryn](https://x.com/Dexoryn)

<p align="center">
  <img src="dexoryn_tg.jpg" height="220" alt="Telegram — @dexoryn" />
  <img src="dexoryn_wechat.png" height="220" alt="WeChat — DexorynWe" />
</p>

---

## Dexoryn Lab

**Dexoryn Lab** is an independent build space focused on **on-chain trading automation**—bots, exchange integrations, and small tools that stay close to real execution (Hyperliquid, CCXT, risk controls, and reproducible strategies). This repository is part of that work: a minimal, readable Python baseline you can extend rather than a black box.

- **Build in public** – Scripts and patterns meant to be forked, audited, and adapted.
- **Community** – For questions, collabs, or custom work, the fastest line is Telegram in **Contact** above; broader updates and context live on X.
- **Latest note** – Background and direction for this line of releases are summarized in [this X post](https://x.com/Dexoryn/status/2047587827521577416) ([@Dexoryn](https://x.com/Dexoryn)).
