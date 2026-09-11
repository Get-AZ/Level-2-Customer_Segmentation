# Interview Preparation

## What problem did you solve?

I built an unsupervised customer-segmentation workflow from Online Retail transaction data using RFM features.

## Why RFM?

RFM summarizes recency, purchasing frequency, and monetary value.

## What was the saved model?

The frozen artifact uses K = 4, random_state = 42, and n_init = 10.

## Was K = 4 statistically optimal?

No. A later reconciliation found K = 2 had a silhouette score of 0.895825 compared with 0.616228 for K = 4.

## Why retain K = 4?

The K = 4 artifact is reproducible and produces four distinct business profiles. It remains conditional pending documented business justification.

## Verified Model-Selection Reconciliation

The reproducible saved customer-segmentation model uses **K=4** clusters with
`random_state=42` and `n_init=10` on the three-feature RFM modeling space:
`Recency`, `Purchase_Frequency`, and `Total_Spending`.

A subsequent model-selection reconciliation evaluated K=2 through K=10 on
the **same three-feature RFM space**. K=2 produced the highest tested
silhouette score:

- **K=2 silhouette:** 0.895825
- **Saved K=4 silhouette:** 0.616228
- **K=2 advantage:** 0.279597

K=4 is **not statistically optimal** on the tested three-feature RFM space.

Therefore, **K=4 must not be described as statistically optimal**. The saved
K=4 model remains reproducible and internally consistent, but its retention
is **CONDITIONAL** pending a documented business requirement for four
segments.

The small K=4 high-value segment is retained as observed data rather than
automatically removed as an outlier. It contains valid finite customer
records and represents an extreme customer-value profile. No customer-level
CSV is included in the public package.

This reconciliation does not involve retraining, model replacement, or
alteration of the frozen model artifacts.
