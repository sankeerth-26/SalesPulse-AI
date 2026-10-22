# SalesPulse AI — Sales Demand Forecasting & Analytics

An interactive machine learning and business analytics application that analyzes historical retail sales, forecasts future demand, and translates sales patterns into actionable business insights.

## 🚀 Overview

SalesPulse AI provides an interactive Streamlit dashboard for exploring retail sales performance, understanding seasonal trends, comparing forecasting models, and generating future sales projections.

The application uses historical transaction data and classical time-series forecasting techniques, including ARIMA and Holt-Winters Exponential Smoothing, to support data-driven inventory planning and business decisions.

## ✨ Key Features

- **Executive Overview:** Monitor revenue, daily sales performance, and projected sales through summary metrics and visualizations.
- **Sales Trend Analysis:** Explore historical sales trends, moving averages, annual performance, and quarterly revenue.
- **Seasonality Analysis:** Investigate monthly patterns, day-of-week variations, and seasonal demand fluctuations.
- **Demand Forecasting:** Generate future sales projections using ARIMA and Holt-Winters forecasting models.
- **Model Comparison:** Compare forecasting performance using MAE, RMSE, and MAPE.
- **Promotion Analysis:** Explore relationships between discounts, sales, and profitability.
- **Business Insights:** Identify potential inventory planning, promotional pricing, and staffing opportunities.
- **Forecast Export:** Download forecast results as a CSV file.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application and model development |
| Streamlit | Interactive web dashboard |
| Pandas and NumPy | Data processing and numerical operations |
| Statsmodels | ARIMA and Holt-Winters forecasting |
| Scikit-learn | Forecast evaluation metrics |
| Matplotlib and Seaborn | Data visualization |
| Joblib | Loading serialized model artifacts |
| Jupyter Notebook | Exploratory data analysis |

## 📊 Dataset

The project uses a retail transactions dataset stored at `data/sales_data.csv`.

The existing project documentation describes the dataset as containing 9,994 transaction records across 21 columns, covering January 2014 through December 2017.

Key attributes include:

- Order and shipping dates
- Product categories and subcategories
- Sales and quantity
- Discounts and profit
- Geographic information, including region, state, and city

These attributes support historical sales analysis, seasonality exploration, and demand forecasting.

## 🧠 Forecasting Methodology

### 1. ARIMA

Autoregressive Integrated Moving Average models temporal dependencies in a time series and serves as a forecasting benchmark.

The existing pipeline uses an ARIMA(1,1,1) configuration.

### 2. Holt-Winters Exponential Smoothing

Holt-Winters models the level, trend, and recurring seasonal patterns in sales data. The existing pipeline uses additive trend and weekly seasonality.

### 3. Model Evaluation

Forecasting models are evaluated using:

- **MAE:** Mean Absolute Error
- **RMSE:** Root Mean Squared Error
- **MAPE:** Mean Absolute Percentage Error

The project uses chronological evaluation rather than randomly shuffling time-series observations.

### Existing Model Results

The current project's saved evaluation results report the following values:

| Model | MAE | RMSE | MAPE |
|---|---:|---:|---:|
| Holt-Winters | $1,628.40 | $2,611.96 | 244.54% |
| ARIMA(1,1,1) | $1,739.46 | $2,739.40 | 395.32% |

Holt-Winters has lower reported MAE and RMSE in this comparison. However, the high MAPE values indicate substantial percentage forecasting errors and warrant further investigation. These are existing project results, not independently verified benchmarks.

## 📁 Project Structure

```text
Sales-Demand-Forecasting/
├── .streamlit/                 # Streamlit configuration, if present
├── data/
│   └── sales_data.csv          # Historical retail transactions
├── models/
│   ├── forecasting_model.pkl   # Serialized forecasting model
│   ├── forecast_results.csv    # Forecast output
│   └── model_metrics.csv       # Evaluation metrics
├── notebooks/
│   └── sales_forecasting_analysis.ipynb
├── screenshots/                # Dashboard screenshots
├── src/
│   └── train_forecasting_model.py
├── app.py                      # Streamlit application
├── requirements.txt            # Python dependencies
└── README.md
```

## ⚙️ Getting Started

### Prerequisites

- Python 3.11
- Git

### 1. Clone the repository

After the project is published, clone your repository and navigate into it:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd Sales-Demand-Forecasting
```

Alternatively, open your existing project folder directly.

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### 4. Launch the dashboard

```powershell
python -m streamlit run app.py
```

Open the local URL displayed in the terminal, typically:

`http://localhost:8501`

The application expects its dataset and model artifacts to be available in the project directories.

## 🔄 Retraining the Forecasting Models

To regenerate the forecasting model and associated output files, run:

```powershell
python src/train_forecasting_model.py
```

Retraining may take time depending on the dataset and model configuration. Keep a backup of the existing model artifacts before replacing them.

## 🔮 Future Improvements

- Investigate and improve the high MAPE forecasting errors.
- Compare additional forecasting approaches, including seasonal ARIMA and machine learning models.
- Incorporate holidays, promotional events, and other external demand drivers.
- Add product-level and category-level demand forecasting.
- Improve forecast uncertainty estimation and model validation.
- Introduce automated model retraining and monitoring.
- Add interactive filters and downloadable business reports.

## 👨‍💻 Author

**Sankeerth S**

- **GitHub:** [sankeerth-26](https://github.com/sankeerth-26)
- **LinkedIn:** [Sankeerth S](https://www.linkedin.com/in/sankeerth-s-1bbba1294)

## 📌 Project Status

The dashboard runs locally. Further UI customization, validation, licensing verification, and deployment preparation are planned before the public release.

---

*SalesPulse AI — Turning historical sales data into demand insights.*
