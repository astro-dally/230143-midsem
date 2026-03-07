# Dataset Information

## Primary Dataset: 20 Newsgroups (All Categories, Binary Grouping)

**Source:** scikit-learn's `fetch_20newsgroups` (downloaded automatically)

**Categories Used:** All 20 categories, grouped into two macro-classes:

- **Class +1:** comp._, sci._, talk.\* categories
- **Class -1:** alt._, misc._, rec._, soc._ categories

**Preprocessing:**

1. Text data loaded with headers, footers, and quotes removed
2. TF-IDF vectorization with `max_features=3000` and English stop words removed
3. Labels converted to {-1, +1} for SVM formulation per Equation (1)
4. Stratified 80/20 train/test split with `random_state=42`

**Statistics:**

- Total samples: ~18,846
- Training samples: ~15,076
- Test samples: ~3,770
- Features: 3,000
- Sparsity: ~98.7% zeros

**Why This Dataset:**

- Sparse text data (>98% zeros) — matches paper's sparsity assumption (Section 3.3)
- Binary classification — matches paper's SVM formulation
- Large enough (l ≈ 15,000) to demonstrate training speedup since n_bar/2 ≪ l
- Similar domain to paper's benchmark datasets (rcv1, news20 in Table 3)

**Download:** Automatic via scikit-learn. No manual download required.

---

## Secondary Dataset: MNIST Digits 3 vs 8 (Task 3.2 — Failure Mode)

**Source:** scikit-learn's `fetch_openml('mnist_784', version=1)`

**Subset:** Binary classification — digit 3 (→ -1) vs digit 8 (→ +1)

**Preprocessing:**

1. Filtered to only digits 3 and 8
2. Scaled to [0, 1] via `MaxAbsScaler`
3. Subsampled: 1,000 training / 500 test instances
4. Converted to sparse format for fair comparison with text pipeline

**Statistics:**

- Features: 784 (28×28 pixel values)
- Avg nonzeros per instance (n̄): ~170
- Sparsity: ~78% zeros (DENSE compared to text)
- Mapped dimension (degree-2): 308,505

**Why This Dataset:**

- **Dense** data violates the paper's sparsity assumption (Section 3.3, Equation 10)
- Demonstrates that explicit polynomial mapping loses its speed advantage on non-sparse data
- n̄/n ≈ 0.22 vs < 0.01 for text — directly tests Assumption 1 from Task 1.2

**Download:** Automatic via scikit-learn (`fetch_openml`). No manual download required.
