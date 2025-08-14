 Customer Segmentation with Clustering

## 1. Project Overview
This project applies **unsupervised learning** techniques to segment customers based on their purchasing behavior.  
Customer segmentation is a fundamental task in marketing analytics, enabling businesses to personalize marketing strategies, improve customer retention, and increase profitability.

We implement **RFM Analysis (Recency, Frequency, Monetary)** combined with **K-Means Clustering** to identify distinct customer groups.

---

## 2. Problem Statement
Marketing campaigns are often applied uniformly to all customers, which may reduce effectiveness and waste resources.  
By identifying **distinct customer segments**, businesses can tailor strategies to each group, improving ROI and customer satisfaction.

**Research Question:**  
> Can we meaningfully segment customers based on transaction history to inform targeted marketing strategies?

---

## 3. Dataset
- **Source:** [E-Commerce Data (Kaggle)](https://www.kaggle.com/datasets/carrie1/ecommerce-data)  
- **Description:**  
  - Transactions from a UK-based online retailer (2010–2011)
  - Fields: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country
  - ~540,000 records

---

## 4. Methodology
**Step 1 — Data Cleaning**
- Removed missing values and cancelled orders
- Removed transactions with negative/zero quantity or price
- Converted date fields to datetime

**Step 2 — Feature Engineering (RFM Analysis)**
- **Recency:** Days since last purchase
- **Frequency:** Number of unique purchases
- **Monetary:** Total spending

**Step 3 — Data Standardization**
- Scaled features using `StandardScaler` for fair clustering

**Step 4 — Clustering**
- Applied **K-Means clustering**
- Determined optimal `k` using:
  - Elbow Method (inertia)
  - Silhouette Score

**Step 5 — Dimensionality Reduction**
- Used PCA to visualize clusters in 2D

---

## 5. Results

### 5.1 Optimal Number of Clusters
- **Elbow Method:** Suggested `k = 4`
- **Silhouette Score:** Highest around `k = 4`

### 5.2 Cluster Profiles

| Cluster | Recency (days) | Frequency | Monetary (£) | Customer Count | Description |
|---------|----------------|-----------|--------------|----------------|-------------|
| 0       | 43.702685      | 3.682711  | 1359.049284  | 3054           | Price-Sensitive Frequent Buyers|  
| 1       | 248.075914     | 1.552015  | 480.617480   | 1067           | Lapsed or at risk customers    |
| 2       | 7.384615       | 82.538462 | 127338.313846| 13             | Loyal High-Value Customers     |
| 3       | 15.500000      | 22.333333 | 12709.090490 | 204            | Loyal and active customers     |


## 6. Insights & Recommendations
- **Cluster 0:** Win-back campaigns, targeted promotions.
- **Cluster 1:** Onboard with first purchase incentives.
- **Cluster 2:** Offer loyalty rewards, VIP programs.
- **Cluster 3:** Target with discounts and bundled offers.

---

## 7. Technologies Used
- **Python**: pandas, numpy, scikit-learn, seaborn, matplotlib
- **Machine Learning**: K-Means, PCA
- **Data Processing**: StandardScaler
- **Visualization**: Seaborn, Matplotlib


