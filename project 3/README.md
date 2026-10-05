# Project 3: Unsupervised Learning — Customer Segmentation

## Project Objective

The objective of this project is to segment customers using unsupervised learning techniques.

The project applies Principal Component Analysis (PCA) for dimensionality reduction and K-Means clustering to discover customer groups in retail data.

## Key Requirements

- Apply PCA to reduce high-dimensional customer features into 2D and 3D representations.
- Use the Elbow Method to evaluate the suitable number of K-Means clusters.
- Use Silhouette Score to evaluate clustering quality.
- Apply K-Means clustering to create customer segments.
- Translate the resulting clusters into actionable business personas.

## Dataset

The project uses a retail e-commerce dataset containing order, customer, product, payment, shipping, order-status, coupon, referral, and pricing information.

The original dataset contains:

- 1,200 orders
- 1,189 unique customers
- 14 original columns

Customer-level features were engineered from the transaction data to create a richer feature set for segmentation.

## Feature Engineering

Customer-level features include:

- Total Orders
- Total Quantity
- Total Spent
- Average Order Value
- Average Unit Price
- Average Items in Cart
- Unique Products
- Unique Payment Methods
- Unique Referral Sources
- Unique Shipping Addresses
- Unique Order Statuses
- Delivered Orders
- Cancelled Orders
- Returned Orders
- Shipped Orders
- Coupon Usage Count
- Unique Coupons Used
- Customer Lifespan
- Purchase Recency

## Dimensionality Reduction

Before applying PCA, numerical customer features were standardized using `StandardScaler`.

Two PCA representations were created:

- 2D PCA
- 3D PCA

The first two principal components explain approximately 49.10% of the total variance.

The first three principal components explain approximately 59.42% of the total variance.

## Clustering

K-Means clustering was evaluated for different values of K.

The Silhouette Score was used as a mathematical measure of clustering quality.

The highest Silhouette Score was obtained at:

**K = 2**

Therefore, the final K-Means model uses two customer clusters.

## Customer Segments

### Cluster 0 — Standard / One-Time Customers

- Customers: 1,178
- Average Orders: 1.00
- Average Spending: 1,057.07
- Average Quantity: 2.95
- Average Recency: 463.69 days

**Business Persona:**  
These customers are primarily one-time or low-frequency buyers.

**Business Action:**  
Use personalized offers, follow-up campaigns, and targeted promotions to encourage repeat purchases.

### Cluster 1 — High-Value Repeat Customers

- Customers: 11
- Average Orders: 2.00
- Average Spending: 1,775.98
- Average Quantity: 5.45
- Average Recency: 311.45 days

**Business Persona:**  
These customers show repeat purchasing behavior, higher average quantity, and higher total spending.

**Business Action:**  
Use loyalty rewards, premium offers, personalized recommendations, and retention campaigns.

## Visualizations

The project includes:

- Elbow Method plot
- Silhouette Score plot
- 2D PCA customer segmentation
- 3D PCA customer segmentation

All visualizations are stored in the `visualizations` folder.

## Output

The `output` folder contains the customer cluster profile:

- `cluster_profiles.csv`

The project also generates:

- `customer_segmentation_results.csv`

## Conclusion

The K-Means model identified two customer segments in the retail dataset.

Cluster 0 represents the majority of customers with mostly single purchases, while Cluster 1 represents a small group of repeat and higher-spending customers.

These segments can help businesses design different marketing and customer-retention strategies.