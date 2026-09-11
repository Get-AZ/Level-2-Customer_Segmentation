# Verified Results

## Frozen K = 4 Model

- K = 4
- random_state = 42
- n_init = 10
- Recency
- Purchase_Frequency
- Total_Spending

Verified K = 4 silhouette: 0.616228

## Model-Selection Reconciliation

The exact three-feature RFM search produced:

- K = 2 → 0.895825
- K = 3 → 0.594223
- K = 4 → 0.616228
- K = 5 → 0.616500
- K = 6 → 0.598289
- K = 7 → 0.516532
- K = 8 → 0.485874
- K = 9 → 0.478438
- K = 10 → 0.479244

K = 2 has the highest tested silhouette score.

The frozen K = 4 model remains reproducible and internally interpretable, but its preferred business use is CONDITIONAL pending documented business justification for four segments.

## Cluster Counts

- Cluster 0 → 3,054
- Cluster 1 → 1,067
- Cluster 2 → 13
- Cluster 3 → 204
- Total → 4,338
