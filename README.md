# IItMandiQuantFinAndAlgo

This repository is about our intra IIT quant finance and algo trading competition which may or may not have impact on our selection for inter IIT.

## Pine Script Trading Strategies

### HMA-EMA Crossover Strategy with Dynamic Position Sizing

A sophisticated long-only Pine Script strategy that combines technical analysis with advanced risk management.

#### Files:
- `hma_ema_crossover_strategy.pine` - Complete Pine Script strategy implementation
- `STRATEGY_DOCUMENTATION.md` - Comprehensive strategy documentation

#### Key Features:
- **Entry Signal**: 50-period Hull Moving Average crosses above 200-period EMA
- **Dynamic Position Sizing**: Based on trend strength (ADX + HMA slope)
- **Risk Management**: ATR-based trailing stop loss
- **Profit Taking**: Four-tier partial profit system (5%, 10%, 15%, 20%)
- **Visual Interface**: Real-time strategy metrics and signal visualization

#### Quick Start:
1. Copy the Pine Script code from `hma_ema_crossover_strategy.pine`
2. Paste into TradingView Pine Script editor
3. Apply to chart and configure parameters
4. Enable alerts for automated notifications

For detailed usage instructions and strategy explanation, see [STRATEGY_DOCUMENTATION.md](STRATEGY_DOCUMENTATION.md).
