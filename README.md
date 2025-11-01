# **Customer Segmentation using RFM & Clustering**
This project performs customer segmentation on the sales_data_sample.csv dataset. The goal is to identify distinct customer groups based on their purchasing behavior using RFM (Recency, Frequency, Monetary) analysis and three unsupervised clustering algorithms: K-Means, Hierarchical Clustering, and DBSCAN.
The final analysis identifies a clear and actionable 2-cluster solution: Active/High-Value Customers and Lapsed/At-Risk Customers.

## 🚀 **Project Workflow**
The notebook follows a comprehensive data science workflow:
Data Cleaning: Loads the dataset, filters for completed orders (Shipped, Resolved), and handles data types.
Feature Engineering (RFM): Aggregates the data by CUSTOMERNAME to create three core marketing metrics:
Recency (R): Days since the customer's last purchase.
Frequency (F): Total number of unique orders.
MonetaryValue (M): Total sales from the customer.
Data Transformation: Visualizes the RFM distributions, identifies high positive skew and applies a np.log1p transformation (twice on Frequency) to normalize the data, and cales all three features using StandardScaler for clustering.
Outlier Handling: For K-Means and Hierarchical Clustering, outliers are removed using the 1.5*IQR rule to create a cleaner dataset (rfm_scaled_no_outliers_df). For DBSCAN, the full dataset (rfm_scaled_df) is used, as DBSCAN is designed to identify outliers itself.
Modeling & Evaluation: Applies and compares three different clustering algorithms.
