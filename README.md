 Investigating Reinforcement Learning Approaches in Stock Market Trading

A comprehensive research project investigating the application of various Reinforcement Learning (RL) techniques for automated stock trading, focusing on semiconductor industry stocks (AMD and NVIDIA). Features multiple RL algorithms, time series analysis, and performance evaluation metrics.

## Project Overview
- Research into automated trading strategies using RL
- Focus on semiconductor industry leaders (AMD, NVIDIA)
- Implementation of multiple RL algorithms and time series models
- Comprehensive performance analysis and comparison
- Integration of economic indicators and market sentiment

## Research Contributions
1. **Advanced RL Techniques**: Implementation and comparison of multiple RL approaches
2. **Comprehensive Indicators**: Integration of financial, economic, and social indicators
3. **Practical Trading Insights**: Valuable findings for retail investors and institutions
4. **Research Foundation**: Framework for future RL and algorithmic trading research

## Technical Implementation
### Core Technologies
- Python
- TensorFlow/PyTorch
- OpenAI Gymnasium
- Economical & Financial APIs (Federal Reserve, Yahoo Finance)

### RL Algorithms
1. **Deep Q-Learning**
   - Implementation in Simple Trader environment
   - PPO algorithm with stable-baselines3
   - Hyperparameter optimization

2. **Policy-Based Methods**
   - Policy Gradient
   - Policy Gradient with Baseline
   - Actor-Critic with Epsilon-Greedy

3. **Time Series & Deep Learning Integration**
   - ARIMA implementation
   - LSTM networks
   - Hybrid model development

### Data Processing
1. **Data Sources**
   - Minute-interval OHLCV market data of NVDA & AMD in last past 5 years
   - Economic indicators at corresponded time point
   - Financial indicators at corresponded time point
   - Google Trends data at corresponded time point
   - Stock splits information

2. **Preprocessing**
   - Time series alignment
   - Feature engineering
   - Data normalisation
   - Gap handling

### Trading Environments
1. **Simple Trader**
   - Basic trading actions(buy, sell, keep)
   - Fixed percentage trades(only 5%)
   - Benchmark environment

2. **Complex Trader**
   - Continuous action space([-1,1])
   - Dynamic position sizing
   - Advanced trading strategies

## Performance Results

### Model Performance Comparison
| RL Algorithm | Environment | Return (%) | Sharpe Ratio | Max Drawdown ($) | Hit Ratio |
|-------------|-------------|------------|--------------|------------------|-----------|
| Deep Q-learning | Simple | 734.60 | 4.64 | 3,250,999.00 | 0.60 |
| Policy Network | Complex | 585.17 | 4.22 | 3,009,615.92 | 0.59 |
| Policy Network w/Baseline | Complex | 1529.99 | 5.06 | 6,097,173.36 | 0.63 |
| Actor-Critic | Complex | 916.00 | 4.17 | 4,219,444.31 | 0.57 |
| ARIMA Enhanced | Complex | 885.61 | 4.25 | 5,093,333.04 | 0.52 |
| LSTM Enhanced | Complex | 2926.10 | 5.57 | 7,044,308.21 | 0.69 |

### Key Findings
1. **LSTM Superiority**
   - Highest return: 2926.10%
   - Best Sharpe ratio: 5.57
   - Most consistent hit ratio: 0.69

2. **Model Comparisons**
   - Policy Network with Baseline showed strong performance
   - ARIMA enhancement provided minimal improvements
   - Simple methods showed lower but stable returns

3. **Risk-Return Dynamics**
   - Higher returns associated with increased drawdown risk
   - Complex models showed better risk-adjusted performance
   - Time series integration improved prediction accuracy
