# 💳 Credit Card Customer Segmentation

📊 Clustering-based segmentation of credit card customers using key spending behavior features. PCA and KMeans clustering are applied to group customers into distinct segments based on their purchasing patterns, cash advances, balance, and credit utilization.

**Dataset Source**: [Credit Card Dataset for Clustering (Kaggle)](https://www.kaggle.com/datasets/arjunbhasin2013/ccdata)

---

## 📁 Project Structure

* **`credit_card_clustering.py`**: Python script containing the complete implementation of exploratory data analysis, dimensionality reduction, clustering, and profiling.
* **`CC GENERAL.csv`**: Raw dataset containing features of customer transactions and credit utilization.

---

## 📝 Dataset Overview

The dataset contains **17 features** describing spending patterns and credit card usage of customers:
- **Features**:
  - `BALANCE`: Average balance amount for the credit card.
  - `PURCHASES`: Total purchase amount made in one cycle.
  - `CASH_ADVANCE`: Amount of cash advances taken by customers.
  - `CREDIT_LIMIT`: Credit limit assigned to customers.
  - `PRC_FULL_PAYMENT`: Ratio of months customers paid their full bill.
  - Other frequency-based and transaction count metrics.
- **Target**: The goal is to segment customers into different clusters to understand their credit spending behavior.

---

## 📈 Key Insights

### Exploratory Data Analysis:
1. **Feature Correlations**:
   - Strong relationships observed between `BALANCE`, `PURCHASES`, and `CREDIT_LIMIT`.
2. **Scatter Plots for Spending Behavior**:
   - Visualized relationships like `PURCHASES` vs `CASH_ADVANCE` and `BALANCE` vs `CREDIT_LIMIT`.

### Data Cleaning:
- Removed `CUST_ID` as it serves as a non-informative identifier.
- Imputed missing values for `MINIMUM_PAYMENTS` and `CREDIT_LIMIT` with median values.

### Feature Scaling:
- Standardized all numerical columns using `StandardScaler` to prepare features for clustering and principal component analysis (PCA).

### Dimensionality Reduction (PCA):
- Reduced dimensions to **7 principal components** while preserving maximum variance.
- Key insights:
  - PCA feature visualization separates clusters effectively.
  - Top principal components (PC1, PC2) explain key variations in customer behavior.

### Customer Segmentation (KMeans):
1. **Elbow Method**:
   - Optimal clusters determined as `k=4`.
2. **Final KMeans Model**:
   - Segmented customers into **4 clusters** with a silhouette score of **0.249**.
3. **Cluster Profiles**:
   - Cluster **0**: High spenders with balanced payments and frequent purchases.
   - Cluster **1**: Low balance, low purchases, and low repayment customers.
   - Cluster **2**: Standard customers with steady and balanced credit utilization.
   - Cluster **3**: High cash advance users with low repayment ratios.

---

## 📊 Visualizations

- **Scatter Plots**:
  - Visualized relationships between `BALANCE`, `PURCHASES`, and `CASH_ADVANCE`.
- **Pair Plots**:
  - Explored multivariate relationships between features like frequency and spending.
- **PCA Plots**:
  - Visualized clusters based on principal components (PC1 & PC2, PC3 & PC4).
- **Elbow Curve**:
  - Determined the optimal number of clusters using inertia (SSE).
- **Cluster Scatter Plots**:
  - Differentiated behavior by plotting clusters using PC1 and PC2.
- **Cluster Profiles**:
  - Aggregated key metrics (`BALANCE`, `PURCHASES`, `CREDIT_LIMIT`, etc.) for each cluster.

---

## 📉 Model Summary:
1. **Silhouette Score**: **0.249** (Moderate cluster separability).
2. **Cluster Size**:
   ```
   CLUSTER
   0     375
   1    4018
   2    3333
   3    1224
   Name: count, dtype: int64
   ```

---

## 🛠️ Tools and Libraries Used

* **Python**: Base language for all data analysis and modeling.
* **Key Libraries**:
  - `pandas` and `numpy`: Data manipulation and cleaning.
  - `seaborn` and `matplotlib`: Visualizations for EDA and clustering.
  - `scikit-learn`: Standardization, dimensionality reduction (PCA), clustering (KMeans), and evaluation.
* **Elbow Method**: Used to determine `k` for optimal cluster segmentation.

---

📫 **Contact**: [www.linkedin.com/in/kanishkayadvv](https://www.linkedin.com/in/kanishkayadvv)  
**Author**: Kanishka Yadav
