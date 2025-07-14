# Highest Pre-market Volume Strategy (Pine Script for TradingView)

This is a Pine Script indicator designed for TradingView that detects breakout trading setups based on pre-market consolidation and price action with volume confirmation.

# Highest Pre-market Volume Strategy

[![Release](https://img.shields.io/github/v/release/lajulajay/highest-premarket-vol-strategy?sort=semver)](https://github.com/lajulajay/highest-premarket-vol-strategy/releases)

## 📂 Project Structure

```text
highest-premarket-vol-strategy/
├── highest-premarket-vol-strategy.pine
├── README.md
├── CHANGELOG.md
├── LICENSE
└── .gitignore
```

## 🚀 Features

### **Core Strategy Requirements:**
- ✅ **Pre-market Volume Analysis**: Compares pre-market volume to historic highest volume
- ✅ **Pattern Detection**: Identifies single strong move up followed by consolidation
- ✅ **Key Level Marking**: Marks resistance/support using candle bodies (not wicks)
- ✅ **Breakout Capture**: Captures actual breakout price with "FIRST BREAKOUT" annotation
- ✅ **Target Marking**: Annotates 5% gain, 1:3 risk:reward, and measured move targets
- ✅ **Pattern Recognition**: Detects retests, bull flags, and ABCD patterns

### **Technical Features:**
- **Pre-market Analysis**: 04:00–09:30 ET session detection
- **Volume Confirmation**: Requires pre-market volume ≥ historic highest threshold
- **Single Move Validation**: Ensures only one strong move followed by consolidation
- **Precise Level Marking**: Uses consolidation high/low (candle bodies)
- **Real-time Breakout Detection**: Captures actual breakout price during regular hours
- **Multiple Target Calculations**: 5% gain, 1:3 R:R, and measured move targets
- **Pattern Annotations**: Retest, bull flag, and ABCD pattern detection
- **Advanced Consolidation Detection**: Bar-to-bar range comparison with consecutive small ranges

### **Visual Customization:**
- **Label Display Controls**: Toggle visibility of level labels and pattern recognition labels
- **Label Size Options**: Choose between tiny, small, or normal label sizes
- **Streamlined Visuals**: Compact display options for crowded charts (especially 1-minute)
- **Background Highlights**: Translucent highlighting for pre-market consolidation and breakout candles
- **Information Table**: Real-time display of volume ratios, levels, and targets

## 📈 Strategy Overview

This indicator implements a comprehensive pre-market volume-based breakout strategy with the following logic:

### **Step 1: Pre-market Pattern Identification**
- Monitors pre-market volume vs historic highest (configurable lookback)
- Detects strong initial move up (configurable minimum %)
- **Advanced Consolidation Detection**: Compares each bar to the previous bar (bar-to-bar range analysis)
- **Consecutive Small Ranges**: Detects consolidation when enough consecutive bars show small ranges
- **Post-Move Analysis**: Only considers bars after the strong move for consolidation detection
- Ensures only one such move occurs (no multiple moves)

### **Step 2: Key Level Marking**
- **Resistance**: Annotated line at pre-market consolidation high
- **Support**: Annotated line at pre-market consolidation low
- Uses candle body levels (not wicks) for precision

### **Step 3: Breakout Capture**
- Monitors for price breakout above pre-market high during regular hours
- Annotates "FIRST BREAKOUT" at actual breakout price
- Triggers alerts for breakout confirmation

### **Step 4: Target Marking**
- **5% Gain**: Entry price + 5%
- **1:3 Risk:Reward**: Entry price + (3 × risk)
- **Measured Move**: Pre-market high + (pre-market high - pre-market low)

### **Step 5: Pattern Recognition**
- **Retests**: Price returning to test breakout level
- **Bull Flags**: Consolidation with lower highs and higher lows
- **ABCD Patterns**: Swing low → higher low → breakout sequence

## 🛠 How to Use

1. **Chart Setup**: Use a **1-minute chart** with **extended hours enabled**
2. **Apply Script**: Copy `highest-premarket-vol-strategy.pine` into Pine Editor
3. **Configure Parameters**: Adjust pre-market volume and pattern detection settings
4. **Monitor Signals**: Watch for pattern identification and breakout alerts

### **Key Parameters:**

#### **Volume Analysis:**
- **1m Pre-market Volume Lookback Days**: Days to calculate historic pre-market volume highest (default: 10 days)
- **5m Pre-market Volume Lookback Days**: Days for 5m confirmation (default: 8 days)
- **Min Pre-market Volume vs Historic Highest**: Volume threshold multiplier (default: 1.5x)

#### **Pattern Detection:**
- **Minimum Move %**: Required percentage move for strong initial move (default: 50%)
- **Consolidation Threshold %**: Maximum range for consolidation (default: 5.0%)
- **Min Consolidation Bars**: Minimum bars for valid consolidation (default: 5)

#### **Display Options:**
- **Show Level Labels**: Display pre-market high/low and breakout labels (default: true)
- **Show Pattern Recognition Labels**: Display bull flag, ABCD, retest labels (default: false)
- **Label Size**: Choose label size - tiny, small, or normal (default: small)
- **Show Targets**: Display target level lines and labels (default: true)

### **TradingView Account Limits:**
The script is optimized for different TradingView account types:

| Account Type | Bar Limit | Recommended Settings | Performance |
|--------------|-----------|---------------------|-------------|
| **Free** | ~5,000 bars | 1m: 5-10 days, 5m: 3-8 days | ✅ Optimized |
| **Pro** | ~10,000 bars | 1m: 10-20 days, 5m: 8-15 days | ✅ Enhanced |
| **Pro+** | ~20,000 bars | 1m: 15-30 days, 5m: 10-25 days | ✅ Extended |
| **Premium** | ~50,000+ bars | 1m: 20-60 days, 5m: 15-50 days | ✅ Maximum |

**Note**: Exceeding bar limits may cause script errors or slow performance. Adjust lookback periods based on your account type.

## 📦 Installation (via GitHub)

```bash
git clone https://github.com/lajulajay/highest-premarket-vol-strategy.git
```

## 🔄 Version History

### **v2.1.0** (Current)
- ✅ **Enhanced Display Controls**: Added label visibility and size options
- ✅ **Streamlined Visuals**: Improved label positioning and reduced chart crowding
- ✅ **Better User Experience**: More intuitive parameter organization
- ✅ **Performance Optimizations**: Improved variable management and error handling
- ✅ **Visual Customization**: Flexible label display for different chart timeframes
- ✅ **Advanced Consolidation Detection**: Bar-to-bar range comparison with consecutive small ranges
- ✅ **Post-Move Analysis**: Only considers bars after strong move for consolidation detection

### **v2.0.0** (Previous)
- ✅ **Fixed Pre-market Volume Analysis**: Now properly compares pre-market volume to historic highest volume
- ✅ **Improved Pattern Detection**: Correctly identifies single strong move + consolidation
- ✅ **Precise Level Marking**: Uses consolidation high/low (candle bodies, not wicks)
- ✅ **Accurate Breakout Capture**: Captures actual breakout price, not pre-market high
- ✅ **Enhanced Annotations**: "FIRST BREAKOUT" labeling and improved target descriptions
- ✅ **Better Pattern Recognition**: More accurate retest, bull flag, and ABCD detection
- ✅ **Pre-market Volume Requirement Integration**: Pattern only triggers when pre-market volume criteria met

### **v1.0.0** (Initial)
- Basic breakout detection
- Simple target calculations
- Limited pattern recognition

## 🤝 Contributing

This script now fully implements the specified requirements with enhanced visual customization. PRs welcome for:
- Enhanced pattern detection algorithms
- Additional technical indicators
- Improved visualization options
- Performance optimizations

## 🔖 Version

**Current Version:** `v2.1.0`  
Complete implementation of highest pre-market volume strategy with enhanced display controls and visual customization.

[View release notes →](https://github.com/lajulajay/highest-premarket-vol-strategy/releases/tag/v2.1.0)
