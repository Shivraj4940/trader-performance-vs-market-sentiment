# Trader Performance vs Market Sentiment Analysis

## Project Overview

This project analyzes the relationship between **cryptocurrency trader performance** and **Bitcoin market sentiment** using historical trading data from Hyperliquid and the Bitcoin Fear & Greed Index.

The objective is to investigate how market sentiment influences trader behavior, profitability, trading frequency, and overall performance through statistical analysis, feature engineering, data visualization, and trader segmentation.

This project was completed as part of the **Primetrade.ai Data Science Internship Assignment**.

---

## Project Objectives

- Clean and preprocess historical trading and market sentiment datasets.
- Engineer daily trader performance and behavioral features.
- Merge trader activity with the Bitcoin Fear & Greed Index.
- Analyze trader performance under Fear and Greed market conditions.
- Segment traders based on trading behavior.
- Perform statistical testing to validate observed differences.
- Create visualizations to communicate key findings.
- Develop actionable trading strategy recommendations.
- Build a simple machine learning model for trader profitability prediction.
- Develop an interactive Streamlit dashboard.

---

## Dataset

The project uses two datasets:

1. **historical_data.csv**
   - Hyperliquid trader transaction history
   - Includes trade-level information such as:
     - Account
     - Coin
     - Side (Buy/Sell)
     - Closed PnL
     - Trade Size
     - Execution Price
     - Timestamp

2. **fear_greed_index.csv**
   - Bitcoin Fear & Greed Index
   - Contains daily market sentiment classification:
     - Extreme Fear
     - Fear
     - Greed
     - Extreme Greed

> **Note:** The `historical_data.csv` file is not included in this repository because of GitHub file upload limitations. Please place the dataset inside the `data/` folder before running the notebook.

---

## Project Structure

```
trader-performance-vs-market-sentiment/
│
├── data/
│   ├── historical_data.csv
│   └── fear_greed_index.csv
│
├── notebooks/
│   └── Trader_Performance_vs_Market_Sentiment.ipynb
│
├── images/
│   ├── chart1_pnl_distribution.png
│   ├── chart2_trade_frequency.png
│   ├── chart3_position_exposure.png
│   ├── chart4_winrate.png
│   └── chart5_long_short_heatmap.png
│
├── app.py
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn
- Streamlit
- Jupyter Notebook

---

## Methodology

### Step 1 – Data Preparation

- Loaded both datasets.
- Checked dataset dimensions.
- Identified missing values and duplicates.
- Converted timestamp columns into datetime format.
- Created a daily trade date.

### Step 2 – Feature Engineering

Generated daily trader metrics including:

- Daily PnL
- Total Trades
- Win Rate
- Average Trade Size
- Position Exposure Proxy
- Long Trades
- Short Trades
- Long/Short Ratio
- Drawdown Proxy

Merged trader metrics with the Fear & Greed Index using the trading date.

### Step 3 – Behavioral & Performance Analysis

Compared trader behavior between Fear and Greed market conditions using:

- Mean
- Median
- Standard Deviation

Performed Mann–Whitney U Tests to determine statistical significance.

### Step 4 – Trader Segmentation

Segmented traders into:

- High Exposure vs Low Exposure
- Frequent vs Infrequent Traders
- Consistent Winners vs Inconsistent Traders

Compared segment performance across different market sentiment conditions.

### Step 5 – Data Visualization

Generated visualizations including:

- Daily PnL Distribution
- Trade Frequency Analysis
- Position Exposure Comparison
- Win Rate Distribution
- Long vs Short Trading Bias

### Step 6 – Strategy Recommendations

Developed actionable trading rules based on behavioral insights obtained from the analysis.

### Step 7 – Bonus

- Built a Random Forest model to predict trader profitability.
- Developed an interactive Streamlit dashboard.

---

## Statistical Analysis

The project uses the **Mann–Whitney U Test** to compare trader performance under Fear and Greed market conditions.

The analysis showed:

- No significant difference in:
  - Daily PnL
  - Win Rate
  - Average Trade Size
  - Position Exposure
  - Drawdown Proxy

- Significant difference in:
  - Total Number of Trades

This suggests that traders primarily adjust **how frequently they trade** rather than their profitability during different market sentiment conditions.

---

## Key Findings

- Market sentiment significantly influences trading frequency.
- Trader profitability remains relatively stable across Fear and Greed periods.
- High Exposure traders generally maintain larger trade sizes regardless of market sentiment.
- Consistent Winners exhibit more stable performance than Inconsistent Traders.
- Trader segmentation provides deeper insights into behavioral differences than sentiment analysis alone.

---

## Strategy Recommendations

- During Fear market conditions, traders should monitor trading frequency to avoid excessive market exposure.
- High Exposure traders should manage position sizes carefully during periods of increased market uncertainty.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/trader-performance-vs-market-sentiment.git
```

Move into the project directory:

```bash
cd trader-performance-vs-market-sentiment
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Run the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```
notebooks/Trader_Performance_vs_Market_Sentiment.ipynb
```

---

## Run the Streamlit Dashboard

```bash
streamlit run app.py
```

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scipy
scikit-learn
streamlit
jupyter
```

---

## Future Improvements

- Incorporate additional market indicators.
- Include leverage and margin information when available.
- Evaluate advanced machine learning models such as XGBoost and LightGBM.
- Perform time-series forecasting for trader profitability.
- Deploy the dashboard using Streamlit Cloud.

---

## Author

**Shivraj Salate**

M.Sc. Statistics

Aspiring Data Analyst | Data Scientist | Power BI Developer

---

## License

This project is licensed under the MIT License.
