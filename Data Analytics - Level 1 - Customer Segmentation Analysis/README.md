# Customer Segmentation Analysis

## Objective

The objective of this project is to segment an e-commerce company's customer base based on purchasing behaviour. The analysis uses RFM (Recency, Frequency, Monetary) analysis and K-Means clustering to identify meaningful customer segments and support targeted marketing strategies.

## Dataset

The project uses the **Online Retail Dataset** from the UCI Machine Learning Repository.

The dataset contains transaction-level information from an online retail business, including invoice numbers, products, quantities, transaction dates, prices, customer IDs, and countries.

Dataset Source:
https://archive.ics.uci.edu/dataset/352/online+retail

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Methodology

### 1. Data Inspection

The dataset was inspected to understand:

- Dataset structure and dimensions
- Missing values
- Duplicate records
- Data types
- Unique customers and invoices
- Invalid and inconsistent transaction values

### 2. Data Cleaning

The following data-cleaning steps were performed:

- Removed duplicate records
- Removed transactions with missing Customer IDs
- Removed cancelled invoices
- Removed transactions with negative quantities
- Removed transactions with non-positive unit prices

A new `TotalAmount` feature was calculated as:

**Total Amount = Quantity × Unit Price**

### 3. Descriptive Analysis

Customer purchasing behaviour was analysed using:

- Average Purchase Value
- Purchase Frequency
- Customer Lifespan
- Estimated Historical Customer Lifetime Value (CLV)

### 4. RFM Analysis

Three behavioural features were selected for customer segmentation:

- **Recency** – Number of days since the customer's most recent purchase
- **Frequency** – Number of unique invoices/purchases made by the customer
- **Monetary** – Total amount spent by the customer

### 5. Customer Lifetime Value

An estimated historical CLV was calculated using:

**Estimated CLV = Average Purchase Value × Purchase Frequency × Customer Lifespan (Years)**

This represents a historical estimate based on observed transactions and is not a predictive CLV model.

### 6. Data Transformation and Standardization

The RFM variables showed significant right-skewness, particularly Frequency and Monetary values.

A log transformation using `log1p()` was applied to reduce the influence of extreme values, followed by standardization using `StandardScaler`.

### 7. K-Means Clustering

The K-Means clustering algorithm was applied to the standardized RFM features.

The Elbow Method was used to determine a suitable number of clusters.

Based on the Elbow Method, **4 clusters** were selected as a practical solution.

### 8. Customer Segment Profiling

The four identified customer segments were:

1. **Champions / High-Value Loyal Customers**
2. **At-Risk / Inactive Low-Value Customers**
3. **Recent / Potential Customers**
4. **Loyal / Regular Customers**

## Customer Segments

### Champions / High-Value Loyal Customers

These customers have:

- Very recent purchases
- High purchase frequency
- High monetary value
- High estimated historical CLV

**Marketing Strategy:**
- VIP loyalty programmes
- Exclusive offers
- Early access to new products
- Premium and complementary product recommendations

### At-Risk / Inactive Low-Value Customers

These customers have:

- High recency values
- Low purchase frequency
- Low monetary value
- Low estimated historical CLV

**Marketing Strategy:**
- Win-back campaigns
- Personalized discounts
- Re-engagement emails
- Limited-time offers

### Recent / Potential Customers

These customers have:

- Very recent purchases
- Low purchase frequency
- Relatively low monetary value

**Marketing Strategy:**
- Encourage repeat purchases
- Personalized product recommendations
- Next-purchase incentives
- Product bundles and cross-selling

### Loyal / Regular Customers

These customers have:

- Moderate recency
- Regular purchase activity
- Higher monetary value than recent/potential customers

**Marketing Strategy:**
- Loyalty rewards
- Personalized promotions
- Product bundles
- Encourage movement toward the high-value customer segment

## Visualizations

The project includes:

- Elbow Method plot
- Recency vs Monetary Value scatter plot
- Purchase Frequency vs Monetary Value scatter plot
- Average Monetary Value by Customer Segment
- Customer count by cluster

## Key Insights

- Champions / High-Value Loyal Customers represent the most valuable customer group.
- At-Risk / Inactive Low-Value Customers show the lowest purchasing activity.
- Recent / Potential Customers provide an opportunity for future growth.
- Loyal / Regular Customers form a stable customer base with regular purchasing behaviour.
- Customer spending is highly right-skewed, making log transformation useful before clustering.
- Different customer segments require different marketing strategies.

## Business Recommendations

The business can use the identified customer segments to:

1. Prioritize retention of high-value customers.
2. Re-engage inactive customers through targeted win-back campaigns.
3. Encourage recent customers to make repeat purchases.
4. Reward regular customers and gradually move them toward higher-value segments.
5. Allocate marketing resources based on customer value and purchasing behaviour.

## Files

- `Customer_Segmentation_Analysis.ipynb` – Complete Jupyter Notebook containing data cleaning, RFM analysis, clustering, visualizations, insights, and recommendations.
- `README.md` – Project documentation.

## Conclusion

This project demonstrates how RFM analysis and K-Means clustering can be used to transform transaction-level e-commerce data into meaningful customer segments.

The four identified segments provide actionable insights into customer purchasing behaviour and can help businesses improve customer retention, personalize marketing campaigns, encourage repeat purchases, and focus resources on high-value customers.
