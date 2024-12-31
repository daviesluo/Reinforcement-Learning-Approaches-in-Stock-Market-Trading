# Investigating Reinforcement Learning Approaches in Stock Market Trading

## Introduction
The financial industry and stock market analysis have been transformed by digital advancements, particularly with the rise of artificial intelligence. The semiconductor sector, crucial to the third industrial revolution, presents a compelling case study through industry leaders AMD and Nvidia. This research investigates Reinforcement Learning (RL) applications in automated stock trading, aiming to optimize investment strategies through various RL algorithms, including policy networks and deep Q-networks.

### Research Objectives
1. Advancement of RL techniques in financial markets
2. Integration of comprehensive market indicators
3. Development of practical trading strategies
4. Establishment of a research foundation for future work

## Dataset Features and Structure
### Market Data (1-minute intervals, 2019-2024)
- **NVIDIA & AMD OHLCV Data**
  - Open price
  - High price
  - Low price
  - Close price
  - Trading volume
  - Shares split information calculated in

### Financial Indices
- S&P 500 Index
- NASDAQ-100 Index
- PHLX Semiconductor Index

### Economic Indicators
- Inflation Rate
- Federal Reserve Interest Rate
- Effective Federal Fund Rate
- Consumer Confidence Index
- Oil Prices
- Gold Prices

### Social Metrics
- Google Trends data for "AMD" and "Nvidia"

## Reinforcement Learning Environment

### OpenAI Gymnasium Implementation
The trading environment is built on OpenAI Gymnasium, customized for financial market simulation. The environment follows a Markov Decision Process (MDP), defined by the tuple $(S, A, P, R, γ)$:

#### MDP Components
- $S$: State space (market conditions, portfolio status)
- $A$: Action space (trading decisions)
- $P(s'|s,a)$: Transition probability
- $R(s'|s,a)$: Reward function
- $γ$: Discount factor (0 < γ < 1)

#### Environment Structure
1. **Action Space**
   - Continuous vectors for trading decisions
   - Range: [-1, 1] for position sizing
   - Action interpretation:
     - Positive: Buy order
     - Negative: Sell order
     - Zero: Hold position

2. **Observation Space**
   - Multi-dimensional market data array
   - Features:
     - OHLCV data
     - Economic indicators
     - Technical indicators
     - Sentiment metrics

3. **Initial Conditions**
   - Starting balance: $1,000,000
   - Zero initial positions
     
## Trading Agent Implementation
### Simple Trader
- **Actions**: Buy/Sell/Hold with fixed 5% allocation
- **Decision Logic**:
  - Buy: Purchase 5% of current balance
  - Sell: Liquidate 5% of held shares
  - Hold: No action
- **Purpose**: Baseline performance benchmark

### Complex Trader
- **Continuous Action Space**: [-1, 1]
- **Decision Logic**:
  - Positive value (0 to 1): Buy a proportional amount
  - Negative value (-1 to 0): Sell a proportional amount
  - Zero: Hold position
- **Position Sizing**: Dynamic allocation based on model output
- **Advanced Features**: Risk management, position scaling

### Training Strategy
The training process was carefully designed to ensure optimal model performance and learning efficiency:

#### Grid Search Optimization
- **Hyperparameters Explored**:
  - Number of steps per episode
  - Batch size
  - Learning rate
- **Optimization Goal**: Maximize average reward across training runs
- **Validation Process**: 100 episodes with 100 steps each

#### Full Training Implementation
- **Duration**: 20,000 episodes
- **Episode Length**: 100 steps per episode
- **Data Sampling**: Random selection from AMD and Nvidia stock data
- **Diversification**: Varied market conditions and scenarios

## Evaluation Metrics

### 1. Cumulative Return
Calculated as: (Final Net Worth / Initial Net Worth) - 1
- Measures the total percentage return over the investment period
- Direct indicator of strategy's absolute performance

### 2. Sharpe Ratio
Calculated as: (Portfolio Return - Risk-free Rate) / Portfolio Standard Deviation
- Evaluates risk-adjusted returns
- Higher values indicate better risk-adjusted performance

### 3. Maximum Drawdown
Calculated as: (Peak Net Worth - Trough Net Worth) / Peak Net Worth
- Measures the largest peak-to-trough decline
- Key risk assessment metric

### 4. Hit Ratio
Calculated as: Number of Profitable Trades / Total Number of Trades
- Measures trading accuracy and consistency
- Higher ratios indicate a more reliable strategy

## Model Performance Comparison

| Model Type | Return (%) | Sharpe Ratio | Max Drawdown ($M) | Hit Ratio |
|------------|------------|--------------|-------------------|-----------|
| LSTM Enhanced Policy Gradient | 2926.10 | 5.57 | 7.04 | 0.69 |
| Policy Network with Baseline | 1529.99 | 5.06 | 6.10 | 0.63 |
| Actor-Critic with Epsilon-Greedy | 916.00 | 4.17 | 4.22 | 0.57 |
| Deep Q-Learning | 734.60 | 4.64 | 3.25 | 0.60 |
| ARIMA Enhanced Policy Network | 885.61 | 4.25 | 5.09 | 0.52 |

## LSTM-Enhanced Model Performance Analysis
![Performance of Policy Networks integrated with LSTM](LSTM_performance.png)
### Performance Plot Analysis

1. **Total Reward per Episode**
   - Stable learning progression
   - Consistent improvement trend
   - Final convergence around reward value 3
   - Minimal volatility in later episodes

2. **Cumulative Reward per Year**
   - Progressive improvement across episodes
   - Clear differentiation between early and late episodes
   - Strong performance in recent periods
   - Effective learning pattern establishment

3. **Stock Price over Time**
   - Accurate tracking of both AMD and Nvidia
   - Successful capture of market trends
   - Effective handling of price volatility
   - Clear visualization of price movements

4. **Action Distribution**
   - Strategic trading decisions
   - Well-balanced buy/sell ratio
   - Appropriate holding periods
   - Effective market timing

5. **Money Transactions**
   - Efficient capital utilization
   - Strategic position sizing
   - Risk-aware trading execution
   - Profitable trade management

6. **Net Worth Evolution**
   - Consistent portfolio growth
   - Effective drawdown management
   - Superior risk-adjusted returns
   - Sustainable wealth accumulation
