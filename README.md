# Recession Prediction Using Bond Yields

##  Project Structure

```
Recession_BondsYield/
├──  data/                          # Raw and processed data files
│   ├── GS10.csv                      # 10-Year Treasury Constant Maturity Rate
│   ├── GS3M.csv                      # 3-Month Treasury Constant Maturity Rate
│   ├── USREC.csv                     # US Recession indicator data
│   └── yield_merged.csv              # Merged dataset for analysis
│
├──  notebooks/                     # Jupyter notebooks for analysis
│   ├── 01_explore_and_merge.ipynb    # Data exploration and merging
│   ├── 02_logistic_modeling.ipynb    # Logistic regression modeling
│   └── 03_predict_realtime.ipynb     # Real-time prediction implementation
│
├──  outputs/                       # Model outputs and artifacts
│   └── model/                        # Trained model files
│       ├── logistic_model.pkl        # Serialized logistic regression model
│       └── scaler.pkl                # Feature scaler for preprocessing
│
├──  requirements.txt               # Python dependencies
├──  README.md                      # Project documentation
└── .gitignore                        # Git ignore rules
```

##  Project Overview

This project analyzes the relationship between bond yields and economic recessions using machine learning techniques. The analysis focuses on the yield curve (difference between 10-year and 3-month Treasury rates) as a leading indicator for economic downturns.

##  Key Components

- **Data Sources**: Federal Reserve Economic Data (FRED) for Treasury yields and recession indicators
- **Analysis Pipeline**: Three-stage process from exploration to real-time prediction
- **Model**: Logistic regression for recession probability prediction
- **Outputs**: Trained models and preprocessing artifacts for deployment

## Motivation

Inspired by the New York Fed model, this project uses logistic regression to model recession probability from historical yield spreads. The yield curve has predicted nearly every U.S. recession since 1980.

## Tech Stack

- Python
- pandas, scikit-learn, matplotlib
- Logistic Regression
- Data from [FRED](https://fred.stlouisfed.org/)

## How to Run

1. Clone this repository

2. Open the Jupyter notebooks in the `notebooks/` directory.

3. Run `01_explore_and_merge.ipynb` to clean and prepare the dataset.

4. Then run `02_logistic_modeling.ipynb` to train the model and view predictions.

5. The trained model and scaler will be saved in the `outputs/model/` directory.

##  Results and Insights

### Key Findings

• **Yield Curve Predictive Power**: The logistic regression model effectively captures the predictive power of the yield curve spread (10Y minus 3M Treasury yields), a widely recognized leading indicator of U.S. recessions.

• **Historical Accuracy**: The model consistently produces higher recession probabilities during or just before historical U.S. recessions, including:
  - Early 2000s downturn
  - 2008 financial crisis  
  - COVID-19 recession

• **Inverse Relationship Confirmed**: Visualizations confirm a strong inverse relationship between the yield spread and economic stability—as the spread narrows or inverts, recession risk rises.

• **Institutional Alignment**: By shifting the recession indicator forward by 12 months, the model mimics the approach used by the New York Federal Reserve, aligning closely with institutional forecasting techniques.

• **Forward-Looking Capability**: A forward-looking simulation (in `03_predict_realtime.ipynb`) shows how the model can be used to forecast recession risk over the next 5 years, based on potential interest rate paths.

### Model Performance

The model demonstrates strong predictive capabilities for identifying recession periods, making it a valuable tool for economic forecasting and risk assessment.
