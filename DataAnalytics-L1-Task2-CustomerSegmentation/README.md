# Customer Segmentation Analysis

## Project Overview

This project focuses on segmenting an e-commerce company's customers based on their purchasing behaviour. The analysis uses RFM (Recency, Frequency, Monetary) analysis and K-Means clustering to identify distinct customer segments.

The resulting customer segments can help businesses understand customer behaviour and develop targeted marketing and retention strategies.

## Objective

The main objectives of this project are:

- Analyze customer purchasing behaviour.
- Clean and prepare the customer transaction data.
- Calculate descriptive statistics such as average purchase value, purchase frequency, and customer lifetime value.
- Create RFM features for customer segmentation.
- Standardize the RFM features.
- Apply K-Means clustering.
- Use the Elbow Method to determine the optimal number of clusters.
- Visualize customer segments using scatter plots.
- Profile and interpret each customer segment.
- Identify suitable marketing strategies for different customer groups.

## Dataset

The project uses the Online Retail II dataset.

The dataset contains e-commerce transaction information including:

- Invoice
- StockCode
- Description
- Quantity
- InvoiceDate
- Price
- Customer ID
- Country

The dataset file used for the analysis is:

online_retail_II.xlsx

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Methodology

### 1. Data Loading and Inspection

The dataset was loaded and inspected to understand its structure, columns, missing values, duplicate records, and inconsistent data.

### 2. Data Cleaning

The data was cleaned by checking:

- Missing values
- Duplicate records
- Inconsistent transaction data
- Invalid or unsuitable records for customer-level analysis

### 3. Descriptive Statistics

Customer-level statistics were calculated, including:

- Average Purchase Value
- Purchase Frequency
- Customer Lifetime Value

### 4. RFM Analysis

RFM analysis was used to represent customer purchasing behaviour.

Recency: Number of days since the customer's most recent purchase.

Frequency: Number of unique invoices associated with the customer.

Monetary: Total amount spent by the customer.

These features were used for customer segmentation.

### 5. Feature Standardization

The RFM features were standardized using StandardScaler so that features with different scales could be used effectively by the K-Means algorithm.

### 6. K-Means Clustering

K-Means clustering was applied to divide customers into groups with similar purchasing behaviour.

The Elbow Method was used to determine a suitable number of clusters.

The final analysis used 4 customer clusters.

### 7. Data Visualization

Customer segments were visualized using scatter plots showing relationships between RFM features.

A bar chart was also created to compare the number of customers in each cluster.

## Customer Segment Profiles

| Cluster | Recency | Frequency | Monetary |
|---|---:|---:|---:|
| Cluster 0 | 43.03 | 4.46 | 1,710.65 |
| Cluster 1 | 242.98 | 1.66 | 593.54 |
| Cluster 2 | 5.60 | 113.60 | 215,535.00 |
| Cluster 3 | 14.91 | 47.02 | 28,896.42 |

## Cluster Interpretation

### Cluster 0 — Regular/Moderate-Value Customers

These customers show moderate recency, frequency, and monetary values. They represent customers with regular but comparatively lower purchasing activity.

Suggested action:
- Personalized offers
- Product recommendations
- Loyalty incentives

### Cluster 1 — At-Risk / Inactive Customers

These customers have high recency values and low frequency and monetary values, indicating that they have not purchased recently and have relatively low purchasing activity.

Suggested action:
- Re-engagement campaigns
- Special discounts
- Personalized reminders
- Win-back offers

### Cluster 2 — High-Value Loyal Customers
These customers have very low recency and extremely high frequency and monetary values. They represent the most valuable and highly engaged customer segment.

Suggested action:
- VIP or loyalty programs
- Exclusive offers
- Premium customer support
- Early access to new products

### Cluster 3 — Valuable Active Customers

These customers have low recency and high frequency and monetary values. They are active customers with strong purchasing behaviour.

Suggested action:
- Loyalty rewards
- Cross-selling and upselling
- Personalized recommendations
- Exclusive promotions

## Key Insights

- RFM analysis successfully represented customer purchasing behaviour.
- K-Means clustering identified four distinct customer segments.
- Cluster 2 represents the highest-value customer group based on frequency and monetary value.
- Cluster 1 contains customers who may require re-engagement and retention strategies.
- Active and high-value customers can be targeted with loyalty programs and personalized offers.
- Customer segmentation can help businesses improve targeted marketing and customer retention.

