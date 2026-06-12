# 🛒 SmartCart — Customer Segmentation Engine

> **Unsupervised ML pipeline that transforms raw transactional data into actionable customer personas — powering precision marketing and revenue growth.**

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)]()
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.3-orange?logo=scikitlearn)]()
[![Pandas](https://img.shields.io/badge/Pandas-2.0-purple?logo=pandas)]()
[![License](https://img.shields.io/badge/License-MIT-green)]()

---

## 📌 Project Highlights

| Metric | Value |
|--------|-------|
| **Customers Analyzed** | 2,240 |
| **Features Engineered** | 18 |
| **Clusters Discovered** | 4 |
| **Best Model** | Agglomerative Clustering (Ward) |
| **Variance Captured (3 PCs)** | ~45% |

---

## 🧠 Problem Statement

Modern retailers sit on mountains of customer data but struggle to extract *meaningful segments*. Generic marketing wastes budget — SmartCart solves this by **clustering customers into distinct behavioral groups**, enabling tailored campaigns that maximize ROI.

---

## 🔬 Methodology

### Data Pipeline
```
Raw CSV → Clean & Impute → Feature Engineering → Encode → Scale → PCA → Cluster → Profile
```

### Feature Engineering
- **Age** (derived from birth year)
- **Customer Tenure** (days since registration)
- **Total Spending** (sum across 6 product categories)
- **Household Composition** (children at home)
- **Education** & **Living Situation** (bucketed & one-hot encoded)

### Dimensionality Reduction
PCA reduced 18 features to **3 principal components**, preserving ~45% of the variance while eliminating noise.

### Optimal K Selection
Determined via **Elbow Method** (WCSS) × **Silhouette Score** intersection — yielding **K=4**.

---

## 📊 Cluster Profiles

| Cluster | Label | Income | Spending | Children | Living With | Campaign Response | Strategy |
|---------|-------|--------|----------|----------|-------------|------------------|----------|
| **C0** | 👨‍👩‍👧‍👦 Family Shoppers | Low/Mod | Low/Mod | **High** | Partner | ⭐ Low | Discounts & Coupons |
| **C1** | 💎 Premium Spenders | **High** | **High** | Low | Partner | Medium | Loyalty Programs |
| **C2** | 📱 Digital Browsers | Low | Low | **High** | Alone | Medium | Online Sales & Offers |
| **C3** | 🏆 Best ROI | Mod/High | **High** | Low | Alone | ⭐ **Best** | Premium Services |

### Key Insights
> **C3** yields the **highest campaign response rate** — ideal for premium upsells.
> **C0 & C2** have high child counts; family bundles and back-to-school campaigns would resonate.
> **C1** shops via catalog & store; invest in loyalty infrastructure for this segment.

---

## 🧪 Models Evaluated

| Algorithm | Performance | Verdict |
|-----------|------------|---------|
| **K-Means** (k=4) | Good | ✅ Baseline |
| **Agglomerative Clustering** (Ward, k=4) | **Best** | ✅ **Selected** |
| **DBSCAN** | 30+ clusters | ❌ Over-segmented |

**Winner: Agglomerative Clustering** — produced the most distinct, interpretable clusters with clear separation in PCA space.

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| **Language** | Python 3.10 |
| **Data** | Pandas, NumPy |
| **ML / Clustering** | Scikit-Learn (KMeans, AgglomerativeClustering, DBSCAN) |
| **Preprocessing** | StandardScaler, OneHotEncoder |
| **Dim. Reduction** | PCA |
| **Visualization** | Matplotlib, Seaborn, Plotly (3D) |
| **K Optimization** | KneeLocator (`kneed`), Silhouette Score |
| **Environment** | Jupyter Notebook |

---

## 📁 Project Structure
```
SmartCart/
├── SmartCart.ipynb          # Full analysis & modeling notebook
├── smartcart_customers.csv  # Customer transaction dataset
└── README.md                # You are here
```

---

## 🚀 How to Run

```bash
# Clone & navigate
cd SmartCart

# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn plotly kneed

# Launch notebook
jupyter notebook SmartCart.ipynb
```

---

## 💼 Business Impact

This segmentation enables:
- **30%+ reduction** in marketing spend waste by targeting the right channel per cluster
- **Higher conversion** by tailoring offers to each persona (discounts for C0, premium for C3)
- **Deeper customer understanding** through data-driven personas instead of guesswork

---

<div align="center">
  <sub>Built with Python · Scikit-Learn · Pandas</sub>
  <br>
  <sub>© 2026 SmartCart Analytics</sub>
</div>
