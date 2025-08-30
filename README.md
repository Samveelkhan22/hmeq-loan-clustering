# 🏦 Home Equity Loan Risk Analysis & Clustering

This project analyzes the **HMEQ (Home Equity Loan) dataset** to explore borrower profiles, handle missing data, and apply unsupervised machine learning (K-Means clustering) to identify customer risk segments.  

The dataset contains information about borrowers at the time loans were issued, along with two key target variables:
- **TARGET_BAD_FLAG**: Indicates if the loan defaulted (1 = default, 0 = repaid).  
- **TARGET_LOSS_AMT**: The amount of money lost when a loan defaulted.  

---

## 📊 Project Workflow

1. **Data Preparation**
   - Loaded data from `HMEQ_Loss.xls` (skipping the title row).
   - Imputed missing numeric values with the **median**.
   - Imputed missing categorical values with the **mode**.
   - Created a numeric-only dataset, excluding target and categorical variables.
   - Standardized features using **StandardScaler**.

2. **Feature Selection for Clustering**
   - Selected three related variables:  
     - `LOAN` (loan amount)  
     - `MORTDUE` (mortgage due)  
     - `VALUE` (property value)  

3. **Cluster Analysis**
   - Used **K-Means clustering**.
   - Determined optimal number of clusters with **Elbow (Inertia)** and **Silhouette Score** plots.
   - Final model used **k = 3 clusters**.

4. **Cluster Profiling**
   - Analyzed average values of selected variables per cluster.
   - Compared clusters against target variables (`TARGET_BAD_FLAG`, `TARGET_LOSS_AMT`).
   - Interpreted financial risk profiles for each cluster.

---

## 📈 Results Summary

- **Cluster 0**: Larger homes & mortgages, moderate loans → relatively stable customers.  
- **Cluster 1**: Higher loan balances but lower property values → lowest default rate, but **highest loss amounts** when default occurs.  
- **Cluster 2**: Smaller loans, moderate properties → **highest default probability**, though losses are smaller.  

### Key Insight:
> Loan size **alone** is not a reliable predictor of default risk.  
> Smaller loans (Cluster 2) have **higher probability of default**, while larger loans (Cluster 1) are less risky but create **bigger losses** when defaults happen.  




## 📂 Repository Structure

