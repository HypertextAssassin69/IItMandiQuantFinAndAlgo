# HMA-EMA Crossover Strategy with Dynamic Position Sizing

## Overview

This Pine Script strategy implements a long-only trading system based on Hull Moving Average (HMA) and Exponential Moving Average (EMA) crossovers. The strategy incorporates dynamic position sizing, advanced risk management, and systematic profit-taking mechanisms.

## Key Features

### 1. Entry Conditions
- **Primary Signal**: 50-period Hull Moving Average crosses above 200-period EMA
- **Trend Confirmation**: ADX above threshold (default: 25) indicating strong trend
- **Momentum Filter**: Positive HMA slope ensuring upward momentum

### 2. Dynamic Position Sizing
The strategy adjusts position size based on trend strength, calculated using:
- **ADX Factor**: Normalized ADX value (0-1 scale)
- **Slope Factor**: Normalized HMA slope strength
- **Combined Trend Strength**: Average of ADX and slope factors
- **Position Size**: Base size + (Max size - Base size) × Trend strength

### 3. Risk Management
- **ATR-Based Trailing Stop**: Dynamic stop loss that trails price using Average True Range
- **Configurable Stop Distance**: ATR multiplier for stop loss distance
- **Position Reset**: All variables reset on new entry

### 4. Profit Taking System
Four-tier partial profit taking system:
- **Level 1**: 5% profit (25% of position)
- **Level 2**: 10% profit (25% of position)
- **Level 3**: 15% profit (25% of position)
- **Level 4**: 20% profit (25% of position)

## Input Parameters

### Moving Average Settings
- `hma_short_length`: Short HMA period for slope calculation (default: 20)
- `hma_long_length`: Long HMA period for entry signal (default: 50)
- `ema_length`: EMA period for crossover signal (default: 200)

### Trend Strength Settings
- `adx_length`: ADX calculation period (default: 14)
- `adx_threshold`: Minimum ADX for trade entry (default: 25)

### Position Sizing Settings
- `base_position_size`: Minimum position size percentage (default: 10%)
- `max_position_size`: Maximum position size percentage (default: 25%)

### Risk Management Settings
- `atr_length`: ATR calculation period (default: 14)
- `atr_multiplier`: ATR multiplier for trailing stop (default: 2.0)

### Profit Taking Settings
- `profit_1` to `profit_4`: Profit target percentages (5%, 10%, 15%, 20%)
- `profit_qty_1` to `profit_qty_4`: Position percentages to close at each level (25% each)

## Strategy Logic

### Entry Process
1. Wait for HMA(50) to cross above EMA(200)
2. Verify ADX > threshold for trend strength
3. Confirm positive HMA slope for momentum
4. Calculate dynamic position size based on trend strength
5. Enter long position with calculated size

### Risk Management Process
1. Set initial trailing stop at entry price - (ATR × multiplier)
2. Update trailing stop as price moves up
3. Close position if price hits trailing stop
4. Reset all tracking variables on position close

### Profit Taking Process
1. Monitor profit percentage from entry price
2. Close partial positions at each profit level
3. Track which levels have been executed
4. Prevent duplicate profit taking at same level

## Visual Elements

### Chart Overlays
- **Blue Line**: HMA(50) - Primary entry signal
- **Red Line**: EMA(200) - Crossover reference
- **Orange Line**: HMA(20) - Slope calculation reference
- **Red Step Line**: Current trailing stop level
- **Yellow Circles**: Active profit target levels

### Entry Signals
- **Green Triangle Up**: Long entry signal

### Information Table
Real-time display of:
- Current ADX value
- HMA slope strength
- Calculated trend strength percentage
- Dynamic position size
- Current ATR value
- Position status
- Entry price (if in position)

## Alerts

### Available Alerts
1. **Long Entry Signal**: Triggered when all entry conditions are met
2. **Trailing Stop Hit**: Triggered when trailing stop is breached

## Usage Instructions

### 1. Platform Setup
- Copy the Pine Script code to TradingView
- Apply to desired chart (works on all timeframes)
- Configure input parameters as needed

### 2. Parameter Optimization
- **Conservative Setup**: Lower base/max position sizes, higher ATR multiplier
- **Aggressive Setup**: Higher position sizes, lower ATR multiplier
- **Market Adaptation**: Adjust ADX threshold based on market volatility

### 3. Risk Considerations
- Strategy is long-only (no short positions)
- Requires trending markets for optimal performance
- May underperform in choppy/sideways markets
- Commission costs can impact profitability on smaller accounts

### 4. Backtesting Recommendations
- Test across different market conditions
- Verify performance across multiple timeframes
- Consider transaction costs in backtesting
- Monitor maximum drawdown periods

## Technical Implementation Details

### Hull Moving Average Calculation
Uses Pine Script's built-in `ta.hma()` function for accurate HMA calculation.

### ADX Implementation
Utilizes `ta.dmi()` function returning directional movement indicators and ADX.

### Dynamic Variables
Uses `var` declarations for persistent state tracking across bars.

### Position Management
Leverages Pine Script's strategy functions for automated position management.

## Performance Considerations

### Strengths
- Trend-following approach captures major moves
- Dynamic sizing improves risk-adjusted returns
- Systematic profit taking locks in gains
- Trailing stop protects against reversals

### Limitations
- May generate false signals in ranging markets
- Requires sufficient trend strength for profitability
- Multiple partial exits can increase transaction costs
- Performance dependent on parameter optimization

## Customization Options

### Entry Modifications
- Add additional filters (volume, momentum oscillators)
- Implement time-based entry restrictions
- Add multiple timeframe confirmation

### Exit Enhancements
- Implement time-based exits
- Add volatility-based position sizing
- Include correlation filters for portfolio management

### Risk Management Extensions
- Add maximum position duration limits
- Implement portfolio heat models
- Include sector/market correlation adjustments

## Version History

- **v1.0**: Initial implementation with core features
- Uses Pine Script v5 for latest functionality
- Includes comprehensive visualization and monitoring tools