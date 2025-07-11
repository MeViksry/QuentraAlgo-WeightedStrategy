# 🚀 QuentraAlgo - Weighted Strategy

<div align="center">

![Pine Script](https://img.shields.io/badge/Pine%20Script-v5-aqua?style=for-the-badge&logo=tradingview&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-aqua?style=for-the-badge&logo=mit&logoColor=white)
![Trading](https://img.shields.io/badge/Trading-Strategy-aqua?style=for-the-badge)

*Strategi trading multi-indikator yang canggih dengan sistem weighted scoring untuk TradingView*

</div>

## 📋 Daftar Isi

- [🎯 Tentang Strategi](#-tentang-strategi)
- [✨ Fitur Utama](#-fitur-utama)
- [🛠️ Komponen Strategi](#️-komponen-strategi)
- [📊 Indikator yang Digunakan](#-indikator-yang-digunakan)
- [⚙️ Pengaturan Parameter](#️-pengaturan-parameter)
- [🎯 Manajemen Risiko](#-manajemen-risiko)
- [📈 Fitur Take Profit](#-fitur-take-profit)
- [🔔 Sistem Alarm](#-sistem-alarm)
- [📱 Instalasi & Penggunaan](#-instalasi--penggunaan)
- [📊 Performa & Analisis](#-performa--analisis)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 🎯 Tentang Strategi

QuentraAlgo Weighted Strategy adalah strategi trading otomatis yang menggunakan sistem scoring berbobot dari 5 indikator teknikal populer. Strategi ini dirancang untuk memberikan sinyal entry dan exit yang lebih akurat dengan menggabungkan kekuatan dari multiple indikator.

### 🌟 Keunggulan Utama

- **🎯 Multi-Indikator**: Menggabungkan 5 strategi berbeda dalam satu sistem
- **⚖️ Weighted Scoring**: Sistem pembobotan yang dapat disesuaikan
- **🛡️ Risk Management**: Stop loss dan take profit yang komprehensif
- **📊 Real-time Monitoring**: Tracking performa dan statistik lengkap
- **🔄 Flexible Configuration**: Pengaturan yang sangat dapat disesuaikan

---

## ✨ Fitur Utama

### 🎮 Trading Features
- ✅ **Long & Short Trading**: Mendukung kedua arah trading
- ✅ **Multi Take Profit**: Hingga 6 level take profit bertahap
- ✅ **Dynamic Stop Loss**: Stop loss yang dapat dipindah secara otomatis
- ✅ **Volume Analysis**: Analisis volume untuk konfirmasi sinyal
- ✅ **Top/Bottom Detection**: Deteksi potensi reversal point

### 📊 Analysis Features
- ✅ **Monthly Performance Table**: Tabel performa bulanan
- ✅ **Real-time Statistics**: Statistik trading live
- ✅ **Visual Signals**: Sinyal buy/sell yang jelas
- ✅ **Trend Highlighting**: Highlight area trend naik/turun

---

## 🛠️ Komponen Strategi

### 1. 📈 Strategy 1: MACD
```pinescript
// MACD dengan MA yang dapat disesuaikan
MA1 = 16 (EMA) - MA2 = 36 (EMA)
Signal = 9 (SMA)
```

### 2. 📊 Strategy 2: Stochastic RSI
```pinescript
// Stochastic RSI untuk momentum
RSI Length = 14
Stochastic Length = 14
Smooth K = 3
```

### 3. 📉 Strategy 3: RSI
```pinescript
// RSI tradisional
Length = 14
Overbought = 77
Oversold = 30
```

### 4. 🎯 Strategy 4: Supertrend
```pinescript
// Supertrend untuk trend following
ATR Period = 2
Multiplier = 2.4
```

### 5. 🔄 Strategy 5: Moving Average Cross
```pinescript
// MA Cross untuk trend confirmation
MA1 = 46 (EMA)
MA2 = 82 (EMA)
```

---

## 📊 Indikator yang Digunakan

| Indikator | Fungsi | Weight Default | Delay |
|-----------|--------|----------------|--------|
| 🔵 MACD | Momentum & Trend | 1 | 1 candle |
| 🟠 Stoch RSI | Overbought/Oversold | 1 | 2 candles |
| 🟢 RSI | Momentum Confirmation | 1 | 2 candles |
| 🔴 Supertrend | Trend Direction | 1 | 1 candle |
| 🟡 MA Cross | Trend Confirmation | 1 | 1 candle |

---

## ⚙️ Pengaturan Parameter

### 🎯 Trading Configuration
```pinescript
// Basic Settings
Initial Capital: $1000
Commission: 0.075%
Default Quantity: 100% of equity
Slippage: 1

// Signal Trigger
Weight Trigger: 2 (minimum score to enter)
```

### 📅 Date Range
```pinescript
From: 1 Jan 2021
To: 1 Jan 9999 (ongoing)
```

### ⚖️ Weight Settings
```pinescript
Strategy 1 (MACD): 1
Strategy 2 (Stoch RSI): 1
Strategy 3 (RSI): 1
Strategy 4 (Supertrend): 1
Strategy 5 (MA Cross): 1
```

---

## 🎯 Manajemen Risiko

### 🛡️ Stop Loss Options
- **📊 Percentage**: Fixed percentage dari entry price
- **🎯 TP-1/TP-2/TP-3**: Move stop ke level TP tertentu
- **🔄 Entry**: Move stop ke entry point (breakeven)

### 📈 Stop Loss Configuration
```pinescript
Stop Loss %: 6.0%
Move Stop Loss Factor: 20%
Stop Source: hl2
```

### 🎯 Take Profit Levels
```pinescript
Max TP Levels: 6
Long TP Each: 6.8%
Long TP Quantity: 15% per level
Short TP Each: 13%
Short TP Quantity: 10% per level
```

---

## 📈 Fitur Take Profit

### 🎯 Multi-Level Take Profit
Strategi ini menggunakan sistem take profit bertahap:

| Level | Long % | Short % | Quantity |
|-------|--------|---------|----------|
| TP-1 | 6.8% | 13% | 15%/10% |
| TP-2 | 13.6% | 26% | 15%/10% |
| TP-3 | 20.4% | 39% | 15%/10% |
| TP-4 | 27.2% | 52% | 15%/10% |
| TP-5 | 34.0% | 65% | 15%/10% |
| TP-6 | 40.8% | 78% | 15%/10% |

### 🔄 Dynamic Stop Loss Management
- Stop loss bergerak sesuai dengan level TP yang tercapai
- Opsi move to breakeven setelah TP tertentu
- Perlindungan profit dengan trailing stop

---

## 🔔 Sistem Alarm

### 📢 Alert Messages
```pinescript
// Entry Signals
Long Entry: "Buy"
Short Entry: "Sell"

// Exit Signals
Close Long: "Close long"
Close Short: "Close short"

// Take Profit
TP Long: "TP long"
TP Short: "TP short"

// Stop Loss
Stop Loss: "SL"
```

### 🎯 Alert Conditions
- Entry berdasarkan weighted score
- Exit berdasarkan reverse signal
- Take profit otomatis
- Stop loss trigger

---

## 📱 Instalasi & Penggunaan

### 🔧 Langkah Instalasi

1. **📥 Download Script**
   ```
   Salin kode Pine Script dari repository
   ```

2. **📊 Buka TradingView**
   ```
   Masuk ke akun TradingView Anda
   ```

3. **⚙️ Pine Editor**
   ```
   Buka Pine Editor (Alt + E)
   Paste kode script
   ```

4. **💾 Save & Apply**
   ```
   Save script dengan nama "QuentraAlgo Weighted Strategy"
   Apply ke chart yang diinginkan
   ```

### 🎯 Penggunaan Optimal

1. **⚙️ Konfigurasi Awal**
   - Set timeframe sesuai trading style
   - Adjust weight parameters
   - Configure risk management

2. **📊 Monitoring**
   - Monitor sinyal entry/exit
   - Track performance metrics
   - Adjust parameters jika diperlukan

3. **🔔 Set Alerts**
   - Enable alert untuk entry signals
   - Set alert untuk exit conditions
   - Configure alert for risk management

---

## 📊 Performa & Analisis

### 📈 Key Metrics Display
Strategi menampilkan metrics real-time:

- **📊 Position Info**: Size, average price, P&L
- **🎯 Next TP**: Target take profit berikutnya
- **🛡️ Stop Price**: Level stop loss aktif
- **📈 Net Profit**: Total profit/loss
- **🎯 Win Rate**: Persentase kemenangan
- **📊 Trade Count**: Jumlah trade yang telah ditutup

### 📅 Monthly Performance Table
Tabel performa bulanan dengan color coding:
- 🟢 **Green**: Profit bulan
- 🔴 **Red**: Loss bulan
- 📊 **Precision**: Dapat disesuaikan (default: 2 decimal)

### 📊 Visual Indicators
- **🔵 Buy Signals**: Label biru untuk long entry
- **🔴 Sell Signals**: Label merah untuk short entry
- **🎯 TP Markers**: Marker untuk take profit levels
- **🛡️ Stop Lines**: Garis stop loss aktif
- **📊 Trend Highlight**: Background highlighting untuk trend

---

## ⚠️ Disclaimer

### 🚨 Risk Warning
- Trading melibatkan risiko kehilangan modal
- Past performance tidak menjamin hasil masa depan
- Selalu gunakan manajemen risiko yang tepat
- Test strategy pada akun demo terlebih dahulu

### 📋 Terms of Use
- Script ini menggunakan Mozilla Public License 2.0
- Gratis untuk penggunaan personal
- Dilarang untuk distribusi komersial tanpa izin
- Pembuat tidak bertanggung jawab atas kerugian trading

### 🔧 Technical Notes
- Kompatibel dengan Pine Script v5
- Optimal untuk timeframe H1 ke atas
- Memerlukan historical data yang cukup
- Performance dapat bervariasi antar asset

---

## 🤝 Kontribusi & Support

### 📞 Contact
- **👨‍💻 Developer**: QuentraAlgo
- **📧 Platform**: TradingView
- **🔗 License**: Mozilla Public License 2.0

### 🎯 Feedback
Jika Anda menemukan bug atau memiliki saran perbaikan:
1. Test pada akun demo
2. Dokumentasikan issue yang ditemukan
3. Berikan feedback konstruktif

---

<div align="center">

### 🌟 Terima kasih telah menggunakan QuentraAlgo Weighted Strategy! 🌟

*Trade with discipline, manage your risk, and let the strategy work for you.*

---

**Made with ❤️ by QuentraAlgo**

</div>