# 📊 PCA Complete Learning Guide

> A beautifully designed, fully interactive HTML guide to **Principal Component Analysis (PCA)** — covering everything from intuition to math to real Python code.

![HTML](https://img.shields.io/badge/HTML-Single%20File-orange?style=flat-square&logo=html5)
![CSS](https://img.shields.io/badge/CSS-Dark%20%2F%20Light%20Mode-blue?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow?style=flat-square)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

---

## 🖥️ Live Preview

Open `PCA_Complete_Guide_v3.html` directly in any browser — **no server, no install, no internet required** (except for Google Fonts on first load).

---

## ✨ Features

| Feature | Description |
|---|---|
| 🌙 Dark / ☀️ Light Mode | Toggle button in the top-right corner. Preference saved in `localStorage` |
| 📋 Copy Code Buttons | Every code block has a one-click copy button with visual feedback |
| 🧭 Sticky Sidebar Nav | Fixed left navigation with active section highlighting as you scroll |
| 📈 Reading Progress Bar | Thin progress line at the top of the page |
| 🔀 Interactive Tabs | Switch between content panels (analogies, use cases, etc.) |
| ✅ Self-Test Quiz | 6-question quiz with instant feedback, explanations, and score tracking |
| 📱 Responsive | Works on mobile, tablet, and desktop |

---

## 📚 Content Overview

### Foundations
- What is PCA? — definition, history, core idea
- Why use PCA? — curse of dimensionality, multicollinearity, visualization, speed
- The Intuition — 3 analogies (photography, shadow, axis rotation), height/weight example

### Mathematics (Step by Step)
- **Step 1** — Standardize the data (Z-score normalization), formula, worked example table
- **Step 2** — Compute the Covariance Matrix, heatmap visualization, code
- **Step 3** — Eigenvalues & Eigenvectors, visual bar chart, formula, code
- **Step 4** — Selecting k components (3 rules: variance threshold, Kaiser rule, Scree plot)
- **Step 5** — Transform the data, inverse_transform / reconstruction, worked example

### In Practice
- Complete Python implementation with `scikit-learn` Pipeline
- How to choose k — decision table by use case
- Understanding Loadings — what components are "made of", interpretation guide

### Applications
- When to use PCA vs when NOT to
- 10 PCA variants and alternatives (Kernel PCA, t-SNE, UMAP, LDA, Autoencoder, etc.)

### Reference
- 14-term Glossary (eigenvalue, eigenvector, covariance matrix, scree plot, etc.)
- 6-question interactive Self-Test Quiz with explanations

---

## 🚀 Quick Start

### Option 1 — Open directly
```bash
# Just double-click the file, or:
open PCA_Complete_Guide_v3.html        # macOS
start PCA_Complete_Guide_v3.html       # Windows
xdg-open PCA_Complete_Guide_v3.html    # Linux
```

### Option 2 — Serve locally
```bash
# Python 3
python -m http.server 8000
# then open http://localhost:8000/PCA_Complete_Guide_v3.html

# Node.js
npx serve .
```

### Option 3 — GitHub Pages
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your guide will be live at `https://yourusername.github.io/your-repo/PCA_Complete_Guide_v3.html`

---

## 🐍 Python Code Covered

All 7 code blocks in the guide are copyable with one click:

```python
# 1. Standardize data
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# 2. Covariance matrix
import numpy as np
X_cov = np.cov(X_scaled.T)

# 3. Eigendecomposition
eigenvalues, eigenvectors = np.linalg.eigh(X_cov)

# 4. Choose k and fit PCA
from sklearn.decomposition import PCA
pca = PCA(n_components=0.95)   # keep 95% variance
X_pca = pca.fit_transform(X_scaled)

# 5. Full pipeline
from sklearn.pipeline import Pipeline
pipeline = Pipeline([
    ('scaler', StandardScaler()),
    ('pca',    PCA(n_components=0.95)),
    ('clf',    LogisticRegression())
])
```

---

## 🎨 Design

- **Font**: [Syne](https://fonts.google.com/specimen/Syne) (headings) + [DM Sans](https://fonts.google.com/specimen/DM+Sans) (body) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) (code)
- **Theme**: Deep navy dark mode by default; clean light blue mode available
- **Colors**: Blue `#5b9bff` · Teal `#2dd4bf` · Amber `#fbbf24` · Green `#4ade80` · Rose `#ff8096`
- **Code highlighting**: GitHub Dark-inspired syntax coloring (keywords, functions, strings, comments, numbers)

---

## 📁 File Structure

```
/
├── PCA_Complete_Guide_v3.html   ← Main file (everything in one file)
├── PCA_Guide.docx               ← Basic PCA guide (Word document)
├── PCA_Problems_Solutions.docx  ← 5 real-world problems (Word document)
├── PCA_Problems_Solutions.html  ← Interactive problems viewer
└── README.md                    ← This file
```

---

## 🧠 Who This Is For

- **Students** in Data Science, ML, or Statistics courses (MSDE / IDSE programs)
- **Developers** who want a quick but thorough reference on PCA
- **Anyone** who wants to understand PCA properly, not just use it as a black box

---

## 📖 Topics Linked to This Guide

PCA is a prerequisite or closely related to:

- `scikit-learn` feature engineering pipelines
- Image compression and computer vision preprocessing
- NLP / text analysis (LSA = TruncatedSVD on text)
- Anomaly detection (reconstruction error)
- Data visualization (scatter plots of PC1 vs PC2)
- Genome-wide association studies (GWAS)
- Financial factor models (Fama-French factors)

---

## 🛠️ Built With

- Pure **HTML + CSS + JavaScript** — zero frameworks, zero build steps
- [Google Fonts](https://fonts.google.com/) — Syne, DM Sans, DM Mono
- `navigator.clipboard` API for copy-to-clipboard (with `execCommand` fallback)
- `localStorage` for theme persistence

---

## 📄 License

MIT License — free to use, modify, and distribute for personal or educational purposes.

---

## 🙏 Acknowledgements

- **Karl Pearson** (1901) — invented PCA
- **Harold Hotelling** (1933) — modern formulation
- **scikit-learn** team — for the excellent Python implementation
- MSDE Program, Cohort 4

---

*Made for the MSDE Data Science Program · PCA Reference Guide*