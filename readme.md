# Stock Price Prediction using Technical Analysis, Machine Learning, and Explainable AI (XAI)

This project investigates the use of technical analysis and machine learning to predict stock prices, using Yuanta 0050 (元大0050) as case studies. It was originally developed for a university seminar, and later extended with Explainable AI (XAI) methods such as SHAP to improve model transparency and interpretability.

---
## 📑 Outline

- [Project Structure](#project-structure)
- [Dataset](#dataset)
- [Methods and Implementation](#methods-and-implementation)
  - [1. Golden Cross Strategy (Technical Analysis)](#1-golden-cross-strategy-technical-analysis)
  - [2. Random Forest (Machine Learning)](#2-random-forest-machine-learning)
  - [3. LSTM (Deep Learning)](#3-lstm-deep-learning)
- [Comparative Analysis](#comparative-analysis)
- [XAI Extension (SHAP Analysis)](#xai-extension-shap-analysis)
- [How to Run](#how-to-run)
- [Future Improvements](#future-improvements)
- [Author](#author)
- [Final Project Poster](#final-project-poster)
- [License](#license)

---

## Project Structure

| Folder          | Description |
|-----------------|-------------|
| `original/`     | Original work submitted during the NCKU Machine Learning Seminar (Golden Cross, Random Forest, LSTM) |
| `xai_extension/`| Post-course extension for explainability using SHAP |
| `assets/`       | Figures, report materials, and supporting documents |

---

## Dataset

- **Data Sources**:
  - `DSO ETF Stock Price History.csv`: Yuanta 0050 (元大0050)
  - `S&P 500 Historical Data.csv`: S&P 500 index data
- **Period**: 2014-01-01 to 2023-11-04

---

## Methods and Implementation

### 1. Golden Cross Strategy (Technical Analysis)
- **Moving Average Parameters**: Short = 5, Long = 20
- **Backtesting Return Rate**: **62.48%**
- **Tools**: Pandas, Matplotlib
- **Strength**: Performs well over long-term periods
- **Notebook**: [`original/golden_cross.ipynb`](original/golden_cross.ipynb)

---

### 2. Random Forest (Machine Learning)
- **Train/Test Split**: 80% training, 20% testing
- **R² Score**: **0.9998**
- **Issue**: Cannot capture time series structure
- **Notebook**: [`original/random_forest.ipynb`](original/random_forest.ipynb)

---

### 3. LSTM (Deep Learning)
- **Input Window**: Past 10 days' features used to predict next day
- **Train/Test Split**: First 80% of time series for training
- **R² Score**: **0.9535**
- **Notebook**: [`original/lstm_snp500.ipynb`](original/lstm_snp500.ipynb)

---

## Comparative Analysis

### Dataset Period

- **Full Range**: 2014-01-02 to 2023-11-03  
- **Prediction Period**: 2021-11-10 to 2023-11-03

### Comparison Approach

- **Golden Cross**: Backtested using actual market trends  
- **Random Forest & LSTM**: Predictions were generated first, then backtested  
- **Golden Cross Parameters**: Short MA = 5, Long MA = 20

### Results

| Model         | Time Awareness | R² Score | Return Rate | Notes                 |
|---------------|----------------|----------|-------------|------------------------|
| Golden Cross  | ✅              | –        | **62.48%**  | Best long-term return |
| Random Forest | ❌              | 0.9998   | Lower       | Likely overfitting    |
| LSTM          | ✅              | 0.9535   | Moderate    | Captures time series  |

### Conclusion

- **Performance Ranking**: **Golden Cross > Random Forest > LSTM**
- **Key Factors**:
  - Timeframe significantly impacts return rates
  - Random Forest, lacking temporal structure, cannot effectively predict future trends despite a high R²
  - Proper hyperparameter tuning is essential for improving ML model performance, especially for LSTM

---

## XAI Extension (SHAP Analysis)

> **Location**: [`xai_extension/`](xai_extension/) (See detail information here.)

After the course, additional analysis was done using SHAP (SHapley Additive Explanations) to explain the LSTM model’s predictions.

- **Tool**: `shap.DeepExplainer` (for TensorFlow/Keras)
- **Visualization**: SHAP summary plot to show feature impact
- **Purpose**: Improve model transparency

📷 Example:

![SHAP Summary Plot](xai_extension/shap_summary.png)

---

## How to Run

### Install dependencies

```bash
pip install -r requirements.txt
```


### Run LSTM prediction

```bash
cd original
jupyter notebook lstm_snp500.ipynb
```

### Run SHAP analysis (after model is trained)

```bash
cd xai_extension
jupyter notebook shap_analysis.ipynb
```

---

## Future Improvements

* Use sentiment analysis (news/social media) as features
* Apply alternative models (e.g., GRU, Transformer, Prophet)
* Deploy demo interface using Streamlit

---

## Author

Created by [Liuian](https://github.com/Liuian)

* 🏫 Originally created for the NCKU Seminar (2023)
* 🔧 XAI analysis and visualization extension done in 2025
* 📬 Open to feedback and collaboration!

---

## Final Project Poster

This project was also presented as a course-end poster in the NCKU Machine Learning Seminar (2023). The poster summarizes the objectives, methods, and key findings of the work.

![Final Poster](https://github.com/Liuian/predict-stock-price_independent-study_NCKU/blob/main/%E4%B8%8D%E5%88%86%E7%B3%BB%E5%B0%88%E9%A1%8C%E6%B5%B7%E5%A0%B1_page-0001.jpg)

---

## License

This project is licensed under the MIT License.


