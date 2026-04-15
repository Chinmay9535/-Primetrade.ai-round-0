**# Primetrade.ai: Trader Performance vs. Market Sentiment**

**\*\*Candidate:\*\* Chinmay D M**

**\*\*Role:\*\* Data Science / Analytics Intern**



**---**



**## Executive Summary**

**This repository contains an exploratory data analysis of trader behavior on Hyperliquid, evaluated against the Bitcoin Fear and Greed Index.** 



**The analysis reveals a highly contrarian ecosystem: high-value accounts operate as informal liquidity providers during market panic ("Extreme Fear"), capturing significant upside. Conversely, retail accounts suffer heavy drawdowns during high volatility and rely entirely on momentum during "Extreme Greed" to achieve profitability.** 



**Based on these findings, this project proposes two data-driven strategies to protect retail capital and optimize platform fee generation.**



**---**



**## Key Findings \& Visual Evidence**



**### 1. Divergent Profitability in Fear vs. Greed**

**High-value accounts achieve their highest average daily PnL during "Fear" conditions. Low-value accounts see profitability drop to near-zero during "Extreme Fear" and peak only during "Extreme Greed" momentum.**



**!\[PnL by Sentiment](insight1\_pnl\_by\_sentiment.png)**



**### 2. Behavioral Shifts (Frequency and Size)**

**Contrary to the assumption that "Greed" drives overtrading, trade frequency peaks significantly during "Extreme Fear" (\~135 avg daily trades) and declines as the market becomes Greedier. This points to high-frequency algorithmic execution or panic selling during volatile drawdowns.**



**!\[Behavioral Shifts](insight2\_behavioral\_shifts.png)**



**### 3. The Contrarian Long/Short Bias**

**The trader base demonstrates contrarian behavior. The Long/Short ratio peaks above 1.0 (net-buying bias) during maximum market panic and drops to its lowest point (\~0.8, net-selling bias) to take profits during "Extreme Greed."**



**!\[Long Short Bias](insight3\_long\_short\_bias.png)**



**---**



**## Strategic Recommendations**



**\*\*1. The Retail Protection Rule (Target: Low-Value Accounts)\*\***

**\* \*\*Observation:\*\* Retail accounts suffer heavy drawdowns during high volatility.**

**\* \*\*Recommendation:\*\* Implement a "High Volatility" UI warning for accounts under a specific capital threshold during 'Extreme Fear' days. Prompting these users to lower leverage can prevent liquidation cascades and preserve platform retention.**



**\*\*2. The Liquidity Provision Rule (Target: High-Value Accounts)\*\***

**\* \*\*Observation:\*\* High-value accounts successfully buy the dip during market panics, stabilizing the ecosystem.**

**\* \*\*Recommendation:\*\* Implement dynamic fee structures that increase maker-fee rebates specifically during 'Extreme Fear' conditions to incentivize institutional participation.**



**---**



**## Bonus: Behavioral Clustering (Trader Archetypes)**

**To move beyond simple median thresholds, an unsupervised K-Means clustering algorithm was applied to the scaled features (Total Trades, Average Trade Size, Overall Win Rate) to segment the ecosystem into three distinct archetypes:**

**1. Retail / Casual**

**2. High-Frequency Algorithmic**

**3. Whales / Institutional**



**!\[Trader Archetypes](bonus\_trader\_archetypes.png)**



**---**



**## Methodology \& Data Engineering**

**\* \*\*Data Ingestion:\*\* Processed 211,224 raw Hyperliquid transactions and 2,644 days of sentiment data. Verified 0 missing values and 0 duplicates.**

**\* \*\*Temporal Alignment:\*\* Standardized transaction timestamps and sentiment logs to a common date object for an exact daily left-join merge.**

**\* \*\*Feature Engineering:\*\* Aggregated transaction logs into 2,340 daily trader summaries, calculating daily PnL, trade count, win rate, and average trade size.**



**---**



**## Reproducibility and Quick Start**



**To reproduce this analysis locally:**



**1. Clone the repository to your local machine.**

**2. Install the required Python packages:**

&#x20;  **```bash**

&#x20;  **pip install -r requirements.txt**

