
---

# E-Commerce Customer Segmentation Project

## Project Overview

This project aims to segment customers of an e-commerce platform based on various demographic and transactional features. The goal is to leverage unsupervised machine learning techniques to identify patterns in customer behavior and group similar customers together. This segmentation will allow the company to better target marketing efforts, improve customer retention, and optimize overall business strategies.

### Project Objectives:
1. **Data Preprocessing**: Clean and preprocess the raw data from multiple sources (Customers, Transactions, Merchants, etc.).
2. **Feature Engineering**: Extract and engineer meaningful features for customer segmentation, such as transaction frequency, coupon usage, and account age.
3. **Clustering**: Apply clustering techniques like K-Means, DBSCAN, and Hierarchical Clustering to group customers.
4. **Cluster Evaluation**: Evaluate clustering performance using metrics like Silhouette Score.
5. **Visualization**: Visualize the customer clusters and provide meaningful insights for business decisions.

## Data Description

The project uses the following datasets:
- **Customers**: Contains information about customers, including demographic details like city and gender.
- **Transactions**: Includes transactional data such as transaction dates, coupon usage, and transaction status (burnt or claimed).
- **Merchants**: Provides details about the merchants and the branches.
- **Branches, Cities, and Genders**: Supplementary datasets to enhance the information related to customers and transactions.

## Project Workflow

### 1. **Data Preprocessing**
- Load and clean data from multiple sheets (Customers, Genders, Cities, Transactions, Branches, Merchants).
- Handle missing values, merge datasets on key columns (e.g., `customer_id`, `branch_id`, `merchant_id`), and ensure data consistency.

### 2. **Feature Engineering**
- Created new features to aid in segmentation:
  - **Transaction Count**: The total number of transactions per customer.
  - **Burnt Count**: The number of burnt coupons per customer.
  - **Claimed Count**: The number of claimed coupons per customer.
  - **Account Age**: The duration between the customer's first and last transaction in days.
  - **Average Transaction Interval**: The average number of days between transactions.
  - **Scaled Features**: Used `StandardScaler` to normalize continuous features like transaction count, burnt count, and account age for clustering.

### 3. **Clustering Techniques**
- **K-Means Clustering**:
  - Performed clustering based on the engineered features.
  - Evaluated the clusters using the **Silhouette Score** to determine the optimal number of clusters.
  - **Silhouette Score** for K-Means was **0.29**.
  
- **DBSCAN**:
  - Applied DBSCAN (Density-Based Spatial Clustering of Applications with Noise) to capture clusters of varying density.
  - Evaluated clustering performance using the Silhouette Score.
  
- **Hierarchical Clustering**:
  - Performed Agglomerative Clustering with different numbers of clusters.
  - Evaluated the clusters using the Silhouette Score, which was **0.31** for Hierarchical Clustering.

### 4. **Cluster Evaluation**
- For each clustering method, the **Silhouette Score** was calculated to assess the clustering quality.
- The scores helped to compare different algorithms and choose the most appropriate one for the data.

### 5. **Visualization**
- **Cluster Distribution**: Visualized clusters for each method using scatter plots and color-coded points based on cluster assignments.
- **Customer Segmentation Profiles**: Provided insights into the different segments by examining the average values of key features within each cluster.
  
## Results and Insights
- The customer segmentation revealed distinct patterns, such as high-frequency users with burnt coupons vs. low-frequency users.
- The clustering methods were compared based on Silhouette Score, with **Hierarchical Clustering** slightly outperforming others.
- Key findings from the segmentation:
  - Customers in certain clusters had much higher coupon burn rates.
  - Account age and transaction frequency were significant drivers of segmentation.

## How to Run the Project

### Prerequisites
- Python 3.x
- Required libraries:
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `seaborn`

### Instructions
1. **Clone the repository** or download the project files.
2. **Install dependencies**: 
    ```bash
    pip install -r requirements.txt
    ```
3. **Run the Jupyter Notebook or Python scripts**:
    - Preprocessing, feature engineering, clustering, and visualization can be executed by running the notebook or the corresponding scripts in sequence.
  
## Files Included
- `E-commerce_data.xlsx`: contains the raw datasets (Customers, Transactions, Genders, etc.).
- `e-commerce.ipynb`: Jupyter Notebook that contains the full workflow, from data preprocessing to clustering and evaluation.


## Future Work
- Apply advanced clustering algorithms (e.g., Gaussian Mixture Models) for comparison.
- Investigate feature selection and dimensionality reduction techniques (e.g., PCA) to improve clustering.
- Perform deeper analysis on each customer segment to inform business strategy.

---
