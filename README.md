# Recession Prediction Using Yield Curve

This project predicts the probability of a U.S. recession in the next 12 months using the yield curve (difference between 10-year and 3-month Treasury yields).

## Motivation

Inspired by the New York Fed model, this project uses logistic regression to model recession probability from historical yield spreads. The yield curve has predicted nearly every U.S. recession since 1960.

## Tech Stack

- Python
- pandas, scikit-learn, matplotlib
- Logistic Regression
- Data from [FRED](https://fred.stlouisfed.org/)

## Project Structure

Recession_BondsYield/
│
├── data/
│   ├── GS3M.csv                 # 3-month Treasury yield
│   ├── GS10.csv                 # 10-year Treasury yield
│   ├── USREC.csv                # Recession indicator
│   └── yield_merged.csv         # Merged and processed dataset
│
├── notebooks/
│   ├── 01_explore_and_merge.ipynb      # Data cleaning and visualization
│   └── 02_logistic_modeling.ipynb      # Model training and prediction
│   └── 03_predict_realtime.ipynb       # Load the models, generate random yields, predict recession
│
├── outputs/
│   └── model/
│       ├── logistic_model.pkl          # Trained logistic regression model
│       └── scaler.pkl                  # StandardScaler used during training
│
└── README.md

## How to Run

1. Clone this repository

2. Open the Jupyter notebooks in the `notebooks/` directory.

3. Run `01_explore_and_merge.ipynb` to clean and prepare the dataset.

4. Then run `02_logistic_modeling.ipynb` to train the model and view predictions.

5. The trained model and scaler will be saved in the `outputs/model/` directory.

## Results and Insights

	•	The logistic regression model effectively captures the predictive power of the yield curve spread (10Y minus 3M Treasury yields), a widely recognized leading indicator of U.S. recessions.

	•	The model consistently produces higher recession probabilities during or just before historical U.S. recessions, including the early 2000s downturn, the 2008 financial crisis, and the COVID-19 recession.

	•	Visualizations confirm a strong inverse relationship between the yield spread and economic stability—as the spread narrows or inverts, recession risk rises.

	•	By shifting the recession indicator forward by 12 months, the model mimics the approach used by the New York Federal Reserve, aligning closely with institutional forecasting techniques.
    
	•	A forward-looking simulation (in 03_predict_realtime.ipynb) shows how the model can be used to forecast recession risk over the next 5 years, based on potential interest rate paths.
