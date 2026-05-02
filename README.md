# Time Series Analysis of Disease Outbreak 📊

A comprehensive time series analysis and forecasting project for modeling disease outbreak patterns using real-world statistical methods.

## 📋 Project Overview

This project analyzes 84 days of X-Flu outbreak data to identify temporal patterns, decompose time series components, and develop forecasting models for predicting future case counts. The analysis demonstrates the application of advanced time series techniques to epidemiological data.

## 🎯 Objectives

- **Identify** temporal patterns in disease outbreak data (trend, seasonality, noise)
- **Decompose** the time series into interpretable components using STL
- **Implement** and compare multiple forecasting models
- **Evaluate** model performance using standard metrics (MAE, RMSE)
- **Forecast** future outbreak trajectory for resource planning

## 📊 Dataset

- **Source**: `Data_Assignment.xlsx`
- **Duration**: 84 days of daily reported cases
- **Format**: Concatenated Day,Cases values (e.g., "120" = Day 1, 20 cases)
- **Range**: 20 to 115 daily cases
- **Key Patterns**:
  - Clear upward trend (disease spread)
  - Weekly (7-day) seasonal pattern (reporting cycles)
  - Random fluctuations (stochastic variations)

## 🔬 Methodology

### 1. Data Exploration & Visualization
- Time series plotting
- Pattern identification (trend, seasonality, noise)
- Statistical summary

### 2. Time Series Decomposition
- **Method**: STL (Seasonal and Trend decomposition using Loess)
- **Period**: 7 days (weekly seasonality)
- **Components**: Trend, Seasonal, Residual

### 3. Forecasting Models

#### Model 1: SARIMA (Seasonal ARIMA)
- **Specification**: SARIMA(1,1,1)(1,1,1,7)
- **Parameters**:
  - AR order: 1
  - Differencing: 1
  - MA order: 1
  - Seasonal period: 7 days

#### Model 2: Exponential Smoothing (Holt-Winters)
- **Type**: Additive model
- **Components**:
  - Trend: Additive
  - Seasonal: Additive
  - Seasonal period: 7 days

### 4. Model Evaluation
- **Train/Test Split**: 70 days training, 14 days testing
- **Metrics**:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
- **Diagnostics**: Residual analysis, ACF plots

## 📈 Key Results

### Model Performance Comparison

| Model | MAE | RMSE | Performance |
|-------|-----|------|-------------|
| **SARIMA** | **3.42** | **3.68** | ✅ Best |
| Exponential Smoothing | 3.95 | 4.21 | ✓ Good |

### Key Findings

- **SARIMA outperformed** Exponential Smoothing with ~15% lower forecast error
- Both models achieved **~3-4% MAPE** on test set (excellent accuracy)
- Strong **weekly seasonality detected** (autocorrelation at lag 7 = 0.98)
- Models successfully captured both **trend and seasonal patterns**
- Forecast accuracy: Average error of 3.42 cases on scale of 90-115 cases

### Residual Analysis

- **SARIMA**: Mean = 0.36, Std = 3.03 (good white noise approximation)
- **Exponential Smoothing**: Mean = 0.00, Std = 1.65 (excellent residuals)
- Both models show minimal autocorrelation in residuals

## 🛠️ Technologies Used

- **Python 3.x**
- **pandas** - Data manipulation
- **numpy** - Numerical computations
- **matplotlib** - Visualization
- **seaborn** - Statistical visualization
- **statsmodels** - Time series analysis (STL, SARIMA, Exponential Smoothing)
- **scikit-learn** - Model evaluation metrics
- **scipy** - Statistical functions

## 📁 Project Structure

```
time-series-disease-outbreak-analysis/
│
├── analysis.ipynb              # Main Jupyter notebook with complete analysis
├── Data_Assignment.xlsx        # Raw dataset (84 days of outbreak data)
├── Case Study Assignment.pdf   # Assignment requirements and specifications
├── verify_analysis.py          # Verification script for data quality checks
├── VERIFICATION_REPORT.md      # Detailed verification and validation report
├── requirements.txt            # Python dependencies (if needed)
└── README.md                   # This file
```

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.7 or higher
pip (Python package manager)
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/gmayank9999/time-series-disease-outbreak-analysis.git
cd time-series-disease-outbreak-analysis
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv .venv
.venv\Scripts\activate  # On Windows
# OR
source .venv/bin/activate  # On macOS/Linux
```

3. **Install required packages**
```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn openpyxl scipy
```

### Running the Analysis

1. **Open Jupyter Notebook**
```bash
jupyter notebook analysis.ipynb
```

2. **Run all cells** sequentially to reproduce the complete analysis

3. **Optional**: Run verification script
```bash
python verify_analysis.py
```

## 📊 Analysis Workflow

The `analysis.ipynb` notebook follows this structure:

1. **Task 1**: Visualization and Pattern Identification
2. **Task 2**: Time Series Decomposition (STL)
3. **Task 3**: Model Implementation (SARIMA & Exponential Smoothing)
4. **Task 4**: Forecasting with Train-Test Split
5. **Task 5**: Model Evaluation and Comparison
6. **Task 6**: Residual Diagnostics
7. **Task 7**: Final Conclusion and Recommendations

## 🎓 Learning Outcomes

This project demonstrates:

- ✅ Time series data preprocessing and exploration
- ✅ Decomposition techniques for understanding components
- ✅ Implementation of SARIMA and Exponential Smoothing models
- ✅ Proper train/test validation methodology
- ✅ Model evaluation using appropriate metrics
- ✅ Residual diagnostics and white noise assessment
- ✅ Professional visualization and reporting

## 📝 Use Cases

This analysis methodology can be applied to:

- 🏥 **Public Health**: Disease outbreak forecasting
- 📈 **Business**: Sales forecasting with seasonality
- 🌡️ **Weather**: Temperature and climate pattern prediction
- 💰 **Finance**: Stock price prediction with trends
- 🚦 **Traffic**: Urban traffic flow forecasting

## 🔍 Key Insights

1. **Weekly Seasonality**: The 7-day pattern reflects systematic reporting cycles typical in healthcare systems
2. **Model Selection**: SARIMA's explicit seasonal differencing proved more effective than exponential smoothing for this data
3. **Forecast Reliability**: 3-4% error rate is excellent for 14-day ahead forecasts in epidemiology
4. **Practical Value**: Models can help public health officials anticipate resource needs

## ⚠️ Limitations

- Analysis assumes stationary patterns continue (no major interventions)
- Limited to 84-day observation period
- Weekly seasonality may not generalize to all outbreak scenarios
- Models don't account for external factors (policy changes, vaccines, etc.)

## 🤝 Contributing

This is an academic project. Feedback and suggestions are welcome!

## 📄 License

This project is for educational purposes.

## 👤 Author

**Mayank Gupta**
- GitHub: [@gmayank9999](https://github.com/gmayank9999)

## 🙏 Acknowledgments

- Case study assignment design
- `statsmodels` library developers
- Open-source Python data science community

---

**Note**: This analysis uses fictional "X-Flu" outbreak data for educational demonstration of time series forecasting techniques.

## 📞 Contact

For questions or collaboration opportunities, please open an issue in this repository.

---

*Last Updated: May 2026*
