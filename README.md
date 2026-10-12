# ⚡ Quanti Engine — Institutional Order-Flow Terminal

[![Release](https://img.shields.io/github/v/release/ElMoorish/Quant-Engine?color=38BDF8&label=Latest%20Release&style=for-the-badge)](https://github.com/ElMoorish/Quant-Engine/releases)
[![Platform](https://img.shields.io/badge/Platform-Windows%20x64-080B11?style=for-the-badge&logo=windows)](https://github.com/ElMoorish/Quant-Engine/releases)
[![Bridge](https://img.shields.io/badge/Bridge-MetaTrader%205-34D399?style=for-the-badge)](https://github.com/ElMoorish/Quant-Engine/releases)
[![License](https://img.shields.io/badge/License-Commercial%20%2F%2024H%20Trial-F6D278?style=for-the-badge)](https://github.com/ElMoorish/Quant-Engine/releases)

> **Official Binary Release Hub.** This repository distributes compiled client binaries, MT5 expert advisors, and setup guides for the Quanti Engine quantitative trading terminal.

---

## 🚀 Quick Download

| Asset | Version | Download | Platform |
| :--- | :--- | :--- | :--- |
| **Quanti Engine Client Bundle** | `v1.0.0` | [⬇️ Download ZIP (3.2 MB)](https://github.com/ElMoorish/Quant-Engine/releases/download/Version/QuantiEngine-v1.0.zip) | Windows 10 / 11 (64-bit) |

*The bundle includes `quanti-engine.exe`, `QuantiTrader.mq5`, `alerts_config.example.json`, and `README_SETUP.txt`.*

---

## 🏛️ What is Quanti Engine?

Quanti Engine is a high-frequency order-flow and microstructure trading terminal built from scratch in Rust and egui. It connects directly to MetaTrader 5 via a sub-microsecond shared-memory ring buffer, bypassing standard broker telemetry lags.

```
┌───────────────────────────┐         < 350ns IPC         ┌───────────────────────────┐
│     MetaTrader 5 (MQL5)   │ ◄─────────────────────────► │     Quanti Engine (Rust)  │
│  Live Broker Tick Stream  │     Shared-Memory Ring      │  Order Flow • Risk Engine │
└───────────────────────────┘                             └─────────────┬─────────────┘
                                                                        │ Direct Webhooks
                                                                        ▼
                                                          ┌───────────────────────────┐
                                                          │   Telegram & Discord VIP  │
                                                          │   Instant Real-Time Alerts│
                                                          └───────────────────────────┘
```

### Core Capabilities

- **300% Diagonal Imbalance Footprint**: Real-time bid/ask order clustering and aggressive delta analysis.
- **Session Volume Profile & Value Area**: Dynamic VPOC, VAH, and VAL tracking for London, Wall Street, and Asian sessions.
- **Regime Invariance (Hurst Exponent)**: Quantitative filter rejecting Brownian random walk noise ($0.47 \le H \le 0.53$) with zero directional edge.
- **Two-Tier Capital Defense**:
  - `+0.70R` Favorable Excursion: Automatically activates **Break-Even Shield** (`entry + spread + 0.05R`).
  - `+1.00R` Favorable Excursion: Engages **Two-Tier Trail** locking in `+0.40R` net profit.
- **Automated Discord & Telegram Webhooks**: Zero-cloud native webhook dispatch for trade entries, shields, and target hits.

---

## 🛠️ 3-Minute Installation Walkthrough

### Step 1: Install the MetaTrader 5 Expert Advisor
1. Download and extract [QuantiEngine-v1.0.zip](https://github.com/ElMoorish/Quant-Engine/releases/download/Version/QuantiEngine-v1.0.zip).
2. In MT5, open **File** $\rightarrow$ **Open Data Folder** $\rightarrow$ `MQL5` $\rightarrow$ `Experts` $\rightarrow$ `Advisors`.
3. Copy `QuantiTrader.mq5` into this folder.
4. In MT5 **Navigator**, right-click **Expert Advisors** and click **Refresh**.
5. Drag `QuantiTrader` onto any chart (e.g. `BTCUSD`, `NAS100`, `US30`).
6. Enable **Algo Trading** and check **Allow DLL imports** in MT5 options (`Ctrl + O`).

### Step 2: Launch the Terminal
1. Double-click `quanti-engine.exe`.
2. The terminal will immediately calibrate your local broker data stream.

### Step 3: Activate Your 24-Hour Free Trial
1. When launched without a key, click **Copy Hardware ID (HWID)**.
2. Send your HWID to your VIP account desk or Telegram bot to receive an instant 24H activation license.
3. Paste the key into the prompt and click **Activate**.

---

## 📊 Curated Institutional Asset Profiles

| Symbol | Market Type | Profile Edge | Spread Ratio | Typical SL |
| :--- | :--- | :--- | :--- | :--- |
| **BTCUSD** | Crypto | Institutional Overlap Momentum | Low | $150.00 pts |
| **NAS100** | US Tech Index | Cash Open Breakout / Reversion | Ultra-Tight | $25.00 pts |
| **US30** | US Industrial | Liquidity Sweep Exhaustion | Tight | $40.00 pts |
| **GER40** | European Index | Frankfurt Open Cash Trend | Ultra-Tight | $15.00 pts |

---

## 📡 Live Telemetry Notifications

To receive your private execution and protection telemetry:
1. Rename `alerts_config.example.json` to `alerts_config.json`.
2. Add your private Discord Webhook URL or Telegram Bot token:
```json
{
  "telegram_bot_token": "YOUR_BOT_TOKEN",
  "telegram_vip_group_id": "YOUR_CHAT_ID",
  "discord_webhook_url": "YOUR_DISCORD_WEBHOOK_URL",
  "send_to_vip": true,
  "send_to_discord": true,
  "alert_on_trade_open": true,
  "alert_on_break_even": true,
  "alert_on_trade_close": true
}
```

---

## ⚖️ Disclaimer

*Quanti Engine is specialized institutional software designed for quantitative analysis, order-flow visualization, and algorithmic trading via MetaTrader 5. Past performance does not guarantee future results. All trading involves capital risk. Test thoroughly on demo accounts before live capital deployment.*
