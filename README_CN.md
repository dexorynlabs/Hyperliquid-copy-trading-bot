# Hyperliquid 实盘交易机器人 – Hyperliquid 上的自动化策略

[English](README.md) | **中文版**

---

## 这是什么？

一个基于 **Python** 的 **Hyperliquid 实盘交易脚本**，通过 **CCXT** 连接交易所，拉取 **K 线数据**，运行 **技术指标策略**（内置 RSI 示例），并可在开仓时附带 **止盈 / 止损** 市价单逻辑。

- **CCXT 对接 Hyperliquid** – 使用钱包地址与私钥
- **RSI 示例策略** – 多空规则可按需替换或扩展
- **风险控制** – 按余额比例仓位、杠杆、逐仓/全仓、止盈止损比例
- **市价单** – 开仓时可附带 TP/SL（见 `HyperliquidClient.place_market_order`）
- **易于扩展** – 在 `compute_indicators()` 中用 `ta` 库增加指标

---

## 5 大优势

1. **自动化执行** – 定时运行脚本即可，无需每笔手动下单。
2. **通用技术栈** – CCXT + pandas + `ta`，资料与社区成熟。
3. **风险参数集中** – 仓位比例、杠杆、保证金模式、止盈止损集中在 `params`。
4. **策略自主** – 可替换 RSI 规则或增加 MACD、布林带等，不必改交易所封装层。
5. **逻辑可读** – 纯 Python 实现，指标到下单路径清晰。

---

## 基础实盘版

本仓库为 **入门实盘脚本**（`hyperliquid-trading-live-bot.py`）。如需深度定制、技术支持或高级功能，请见文末 **联系方式**。

---

## 如何运行

```bash
# 1. 配置环境变量（可用 python-dotenv 写入 .env）
#    HYPERLIQUID_WALLET_ADDRESS
#    HYPERLIQUID_PRIVATE_KEY

# 2. 安装依赖
pip install ccxt pandas ta python-dotenv

# 3. 在 hyperliquid-trading-live-bot.py 中编辑策略（params、ignore_* 等）

# 4. 运行（主网前建议小资金或可用环境下充分测试）
python hyperliquid-trading-live-bot.py
```

**安全提示：** 勿将真实私钥提交到仓库；建议使用独立交易钱包，并只承担可承受损失的资金。

---

## 联系方式

**Telegram：** [@dexoryn](https://t.me/dexoryn)  
**Discord：** dexoryn_  
**X（推特）：** [@Dexoryn](https://x.com/Dexoryn)

<p align="center">
  <img src="dexoryn_tg.jpg" height="220" alt="Telegram — @dexoryn" />
  <img src="dexoryn_wechat.png" height="220" alt="WeChat — DexorynWe" />
</p>

---

## Dexoryn Lab

**Dexoryn Lab** 是一个独立的技术向实验空间，聚焦 **链上交易自动化**：机器人、交易所对接，以及贴近真实成交的小工具（Hyperliquid、CCXT、风控与可复现策略）。本仓库即其中一环：提供一份结构清晰、便于审计和二次开发的 Python 基线，而非封闭黑盒。

- **公开构建** – 脚本与设计便于 fork、审阅与改造。
- **社区** – 咨询、合作或定制请优先使用上文 **联系方式** 中的 Telegram；更完整的动态与语境见 X。
- **最新说明** – 关于这一批发布与方向的梳理，见 [此条 X 动态](https://x.com/Dexoryn/status/2047587827521577416)（[@Dexoryn](https://x.com/Dexoryn)）。
