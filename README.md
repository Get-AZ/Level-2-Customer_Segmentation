# Customer Segmentation — Online Retail

## Project Overview

This project applies unsupervised machine learning to customer-level RFM features derived from Online Retail transaction data.

The objective is to identify meaningful customer segments for customer profiling and business analysis.

## RFM Features

- Recency — days since the customer's most recent purchase.
- Purchase Frequency — number of purchase transactions/invoices.
- Total Spending — total monetary value associated with the customer.

## Methodology

The verified workflow uses:

1. RFM feature construction
2. StandardScaler preprocessing
3. K-Means clustering
4. PCA dimensionality reduction
5. Silhouette-score evaluation
6. Joblib model persistence

## Frozen Saved Model

- Algorithm: K-Means
- K: 4
- random_state: 42
- n_init: 10
- Features: Recency, Purchase_Frequency, Total_Spending

## Important Model-Selection Disclosure

The frozen saved model uses K = 4. However, the later reconciliation audit found that K = 2 has the higher silhouette score on the exact three-feature RFM modeling space.

| Configuration | Silhouette |
|---|---:|
| K = 2 | 0.895825 |
| K = 4 | 0.616228 |

K = 2 therefore has a silhouette advantage of 0.279597.

K = 4 must not be represented as the statistically optimal solution. It is retained as the frozen, reproducible saved model and remains CONDITIONAL pending a documented business justification for four segments.

## Verified K = 4 Profiles

- Cluster 0 — large mainstream customer segment
- Cluster 1 — lower-frequency, lower-spending, less-recent segment
- Cluster 2 — very small extreme high-value segment
- Cluster 3 — high-frequency, high-spending segment

Cluster 2 contains 13 customers. The audit found finite observations with no missing values. It should not automatically be removed as bad data without additional business evidence.

## Reproducibility

The repository contains the verified notebook and frozen model artifacts.

The customer-level derived CSV is intentionally excluded from the public package. See data/README.md.

## Limitations

- Silhouette score alone does not establish business usefulness.
- K = 4 requires documented business justification if presented as the preferred segmentation.
- Cluster 2 requires domain review before removal or merging.
- Customer-level derived data requires publication review.

## Verification Status

- Core artifacts verified: PASS
- Frozen K = 4 reproducibility: PASS
- Cluster assignments: PASS
- Numerical reconciliation: PASS
- Business-profile reconciliation: PASS
- Automatic customer-level dataset publication: FALSE
- K = 4 statistical-optimality claim: NOT SUPPORTED
