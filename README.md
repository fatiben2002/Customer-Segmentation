# Customer Segmentation with Product Embeddings

**Goal.** Build meaningful customer segments from transaction data by clustering product **embeddings** (from item descriptions), aggregating purchases per customer, and then clustering customer profiles.

## Data
- Source: https://www.kaggle.com/datasets/carrie1/ecommerce-data
- Entities: invoices, products, customers.

## Method
1. Clean data (remove cancellations/returns; standardize descriptions).
2. Encode product descriptions with `sentence-transformers` (`all-MiniLM-L6-v2`).
3. Cluster product embeddings (K-Means; k chosen via silhouette).
4. Build customer features (spend per product-cluster, frequency, recency).
5. Cluster customers (scaled features + K-Means).
6. Interpret segments (KPIs + top product categories).

## Results (preview)
- k(products) = X, k(customers) = Y.
- Segments (examples): **High-value frequent**, **Seasonal gifters**, **Low-spend occasional**.
- Example business actions: personalized promos by segment, inventory planning by product cluster.

## Repro
Please use google colab or any other type of notebook interpreter to run this code.
jupyter notebook notebooks/customer_segmentation.ipynb

