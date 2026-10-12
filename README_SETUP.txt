================================================================================
  QUANTI ENGINE — INSTITUTIONAL ORDER-FLOW TRADING TERMINAL
  24-Hour Trial & Client Setup Guide
================================================================================

1. INSTALL MT5 INTEGRATION:
   - Open MetaTrader 5.
   - Click "File" -> "Open Data Folder".
   - Navigate to: MQL5 -> Experts -> Advisors.
   - Copy "QuantiTrader.mq5" into that folder.
   - In MT5 Navigator window, right-click "Expert Advisors" and click "Refresh".
   - Drag "QuantiTrader" onto your BTCUSD, NAS100, or US30 M1 chart.
   - In MT5 Options (Ctrl+O) -> "Expert Advisors" tab:
     * Check "Allow Algo Trading".
     * Check "Allow DLL imports".

2. LAUNCH QUANTI ENGINE:
   - Double-click "quanti-engine.exe".
   - When prompted for a license, copy your 64-character Hardware ID (HWID).
   - Send the HWID to your account representative to receive your 24H Activation Key.
   - Paste the key and click "Activate".

3. OPTIONAL ALERTS CONFIGURATION:
   - Rename "alerts_config.example.json" to "alerts_config.json".
   - Fill in your Discord Webhook URL or Telegram Bot token if you want private alerts.

Support & VIP Desk: https://t.me/your_support_channel
================================================================================
