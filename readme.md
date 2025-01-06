![Image text](https://github.com/Liuian/predict-stock-price_independent-study_NCKU/blob/main/%E4%B8%8D%E5%88%86%E7%B3%BB%E5%B0%88%E9%A1%8C%E6%B5%B7%E5%A0%B1_page-0001.jpg)

# Summary of Implementation Methods

## Raw Data
- **Source**: CSV file downloaded from investing.com (Yuanta 0050, 元大0050).  
- **Period**: January 1, 2014 – November 4, 2023.

### Methods and Results
1. **Golden Cross Strategy**
   - Moving Average Parameters: Short = 5, Long = 20.  
   - Backtesting Return Rate: **62.48%**.  

2. **Random Forest (Machine Learning)**
   - **Training/Test Split**: 80% training, 20% testing.  
   - **R² Score**: **0.9998**.  
   - **Issue**: Lacks time series handling.  

3. **LSTM (Long Short-Term Memory)**
   - Training: Past 10 days' data per iteration.  
   - Training Split: First 80% of data.  
   - **R² Score**: **0.9535**.

### Comparative Analysis
- **Approach**:  
   - Golden Cross: Backtested using actual market trends.  
   - Random Forest & LSTM: Predictions used for backtesting.  

- **Dataset Period**:  
   - Full Range: **2014-01-02 to 2023-11-03**.  
   - Prediction Period: **2021-11-10 to 2023-11-03**.  

- **Golden Cross Parameters**:  
   - Long Moving Average = 20, Short Moving Average = 5.  

### Conclusion
- **Performance Comparison**: Golden Cross > Random Forest > LSTM.  
- **Key Factors**:  
   - Timeframe impacts returns.  
   - Random Forest cannot predict future trends.  
   - Parameter optimization improves results.

---

## 實作方法總結

### 原始資料
- **來源**: 從 investing.com 下載的 CSV 檔 (元大 0050)。  
- **期間**: 2014 年 1 月 1 日 – 2023 年 11 月 4 日。

### 方法與結果
1. **黃金交叉策略**
   - **移動平均參數**: 短均線 = 5，長均線 = 20。  
   - **回測總報酬率**: **62.48%**。  

2. **隨機森林 (機器學習)**
   - **訓練/測試分割**: 80% 為訓練集，20% 為測試集。  
   - **R² 分數**: **0.9998**。  
   - **問題**: 無法處理時間序列資料。  

3. **LSTM (長短期記憶網絡)**
   - **訓練方式**: 每次訓練使用過去 10 天的資料。  
   - 訓練集為前 80% 資料。  
   - **R² 分數**: **0.9535**。

### 綜合比較
- **方法**:  
   - 黃金交叉: 以實際市場走勢進行回測。  
   - 隨機森林與 LSTM: 利用預測數據回測。  

- **數據集範圍**:  
   - 完整範圍: **2014-01-02 至 2023-11-03**。  
   - 預測區間: **2021-11-10 至 2023-11-03**。  

- **黃金交叉參數**:  
   - 長均線 = 20，短均線 = 5。

### 結論
- **績效比較**: 黃金交叉 > 隨機森林 > LSTM。  
- **影響因素**:  
   - 分析期間影響交易回報率。  
   - 隨機森林無法預測未來資料。  
   - 優化參數能提升表現。
