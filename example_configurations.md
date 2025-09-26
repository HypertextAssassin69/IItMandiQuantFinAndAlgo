# Example Strategy Configurations

This file provides several pre-configured parameter sets for different trading styles and market conditions.

## Conservative Configuration
**Best for: Risk-averse traders, volatile markets**

```pinescript
// Moving Average Parameters
hma_short_length = 20
hma_long_length = 50
ema_length = 200

// ADX Parameters
adx_length = 14
adx_threshold = 30.0  // Higher threshold for stronger trends

// Position Sizing Parameters
base_position_size = 5.0   // Lower base size
max_position_size = 15.0   // Lower maximum size

// Risk Management Parameters
atr_length = 14
atr_multiplier = 3.0  // Wider stops

// Profit Taking Parameters
profit_1 = 3.0    // Closer profit targets
profit_2 = 6.0
profit_3 = 10.0
profit_4 = 15.0
```

## Aggressive Configuration
**Best for: Active traders, trending markets**

```pinescript
// Moving Average Parameters
hma_short_length = 15
hma_long_length = 40
ema_length = 150

// ADX Parameters
adx_length = 10
adx_threshold = 20.0  // Lower threshold for more signals

// Position Sizing Parameters
base_position_size = 15.0  // Higher base size
max_position_size = 35.0   // Higher maximum size

// Risk Management Parameters
atr_length = 10
atr_multiplier = 1.5  // Tighter stops

// Profit Taking Parameters
profit_1 = 7.0    // Wider profit targets
profit_2 = 15.0
profit_3 = 25.0
profit_4 = 35.0
```

## Scalping Configuration
**Best for: Short-term traders, lower timeframes**

```pinescript
// Moving Average Parameters
hma_short_length = 10
hma_long_length = 25
ema_length = 100

// ADX Parameters
adx_length = 7
adx_threshold = 25.0

// Position Sizing Parameters
base_position_size = 20.0  // Higher position sizes for quick trades
max_position_size = 40.0

// Risk Management Parameters
atr_length = 7
atr_multiplier = 1.0  // Very tight stops

// Profit Taking Parameters
profit_1 = 1.0    // Very close profit targets
profit_2 = 2.0
profit_3 = 3.5
profit_4 = 5.0

profit_qty_1 = 40.0  // Take larger portions quickly
profit_qty_2 = 30.0
profit_qty_3 = 20.0
profit_qty_4 = 10.0
```

## Swing Trading Configuration
**Best for: Position traders, daily/weekly timeframes**

```pinescript
// Moving Average Parameters
hma_short_length = 25
hma_long_length = 75
ema_length = 300

// ADX Parameters
adx_length = 21
adx_threshold = 25.0

// Position Sizing Parameters
base_position_size = 8.0
max_position_size = 20.0

// Risk Management Parameters
atr_length = 21
atr_multiplier = 2.5

// Profit Taking Parameters
profit_1 = 8.0    // Wider targets for longer holds
profit_2 = 18.0
profit_3 = 30.0
profit_4 = 45.0

profit_qty_1 = 20.0  // Smaller partial exits
profit_qty_2 = 25.0
profit_qty_3 = 30.0
profit_qty_4 = 25.0
```

## Crypto Configuration
**Best for: Cryptocurrency markets**

```pinescript
// Moving Average Parameters
hma_short_length = 20
hma_long_length = 50
ema_length = 200

// ADX Parameters
adx_length = 14
adx_threshold = 20.0  // Lower threshold for crypto volatility

// Position Sizing Parameters
base_position_size = 10.0
max_position_size = 30.0  // Higher for crypto volatility

// Risk Management Parameters
atr_length = 14
atr_multiplier = 2.0

// Profit Taking Parameters
profit_1 = 8.0    // Wider targets for crypto volatility
profit_2 = 18.0
profit_3 = 35.0
profit_4 = 50.0

profit_qty_1 = 30.0  // Heavier initial profit taking
profit_qty_2 = 30.0
profit_qty_3 = 25.0
profit_qty_4 = 15.0
```

## Testing Recommendations

### Backtesting Period
- Minimum 2 years of data
- Include both trending and ranging market conditions
- Test across different market cycles

### Performance Metrics to Monitor
- Total Return
- Maximum Drawdown
- Sharpe Ratio
- Win Rate
- Average Win/Loss Ratio
- Number of Trades

### Optimization Guidelines
1. Start with default parameters
2. Test one parameter group at a time
3. Use walk-forward analysis
4. Avoid over-optimization
5. Consider transaction costs
6. Validate on out-of-sample data

### Market-Specific Adjustments

#### Forex Markets
- Consider lower position sizes due to leverage
- Adjust for different session volatilities
- Account for rollover costs

#### Stock Markets
- Consider earnings announcements
- Adjust for market open/close volatility
- Account for dividend dates

#### Commodities
- Consider seasonal patterns
- Adjust for storage costs
- Account for expiration dates (futures)

## Risk Warnings

⚠️ **Important Disclaimers:**
- Past performance does not guarantee future results
- All trading involves risk of loss
- Never risk more than you can afford to lose
- Always test strategies thoroughly before live trading
- Consider seeking professional financial advice

## Configuration Selection Guide

| Trading Style | Timeframe | Risk Tolerance | Recommended Config |
|---------------|-----------|----------------|-------------------|
| Day Trading | 1m-15m | High | Scalping |
| Swing Trading | 4h-1d | Medium | Swing Trading |
| Position Trading | 1d-1w | Low | Conservative |
| Crypto Trading | Any | High | Crypto |
| Risk Averse | Any | Low | Conservative |
| Risk Seeking | Any | High | Aggressive |