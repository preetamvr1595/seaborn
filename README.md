# Seaborn Mastery Series 📊🎨

[![Python Version](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Seaborn Version](https://img.shields.io/badge/Seaborn-0.13.2-orange.svg)](https://seaborn.pydata.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Welcome to the **Seaborn Mastery Series** repository! This project provides an end-to-end, hands-on, publication-grade curriculum covering **100% of Seaborn features** — from foundational aesthetics and relational plotting to categorical group distributions, joint/pair matrix grids, advanced regression modeling, hierarchical clustering, and the modern **Seaborn Objects API (`seaborn.objects` / `so.Plot`)**.

All notebooks are pre-executed with high-resolution visual output plots embedded directly inside each file.

---

## 📚 Notebook Directory & Curriculum Overview

| Notebook | Focus Area | Key Functions & Features Covered |
| :--- | :--- | :--- |
| **[01_seaborn_basics.ipynb](01_seaborn_basics.ipynb)** | **Themes, Aesthetics & Relational Plots** | `set_theme()`, `set_style()` (`darkgrid`, `whitegrid`, `dark`, `white`, `ticks`), `despine()`, `set_context()`, custom color palettes (`colorblind`, `mako`, `coolwarm`, `diverging_palette`), `scatterplot()`, `lineplot()`, `relplot()`, Figure-Level vs Axes-Level API architecture. |
| **[02_categorical_plots.ipynb](02_categorical_plots.ipynb)** | **Categorical Distributions & Estimates** | `stripplot()`, `swarmplot()`, `boxplot()` (notched), `violinplot()` (split violins, inner quartiles), `boxenplot()`, `barplot()` (custom estimators, SD/CI error bars), `countplot()`, `pointplot()`, `catplot()`, hybrid overlaid plots (Box+Strip, Violin+Swarm). |
| **[03_distribution_plots.ipynb](03_distribution_plots.ipynb)** | **Univariate, Bivariate & Multi-Plot Grids** | `histplot()` (density, step, poly), `kdeplot()` (bandwidth tuning, filled), `ecdfplot()`, `rugplot()`, 2D `kdeplot()`, 2D `histplot()`, `displot()`, `jointplot()` (`hex`, `kde`, `scatter`), `pairplot()` (corner matrix), `JointGrid`, `PairGrid`. |
| **[04_regression_matrix.ipynb](04_regression_matrix.ipynb)** | **Regression, Matrix Heatmaps & Objects API** | `regplot()`, `lmplot()`, `residplot()`, polynomial regression (`order=2`), robust regression (`robust=True`), logistic regression (`logistic=True`), LOWESS smoothing, `heatmap()` (masked triangular correlation), `clustermap()` (hierarchical clustering), Seaborn Objects API (`so.Plot`, `so.Dot`, `so.Line`, `so.Bar`, `so.KDE`, `so.PolyFit`). |
| **[05_titanic_eda.ipynb](05_titanic_eda.ipynb)** | **Real-World Capstone EDA & Dashboard** | End-to-end data cleaning, smart median imputation, feature engineering (`family_size`, `is_alone`, `age_group`, `fare_category`), demographic interaction analysis, logistic survival modeling, and a 4-panel Executive Dashboard (`plt.subplots`). |

---

## 🚀 Getting Started & Installation

### 1. Prerequisites & Environment Setup
Ensure you have Python 3.9+ installed. Clone the repository and install the required dependencies:

```bash
git clone https://github.com/preetamvr1595/seaborn.git
cd seaborn
pip install seaborn matplotlib pandas numpy nbformat nbclient jupyter
```

### 2. Launching the Notebooks
To interactively explore and run the notebooks in Jupyter:

```bash
jupyter notebook
```
Or open any `.ipynb` file in VS Code or JupyterLab.

---

## 🎨 Core Seaborn Concepts Explored

### 1. Figure-Level vs. Axes-Level Architecture
- **Axes-Level Functions** (`scatterplot`, `lineplot`, `barplot`, `histplot`, `heatmap`): Draw directly onto a specified Matplotlib `Axes` object. Ideal for custom multi-panel subplots created via `plt.subplots()`.
- **Figure-Level Functions** (`relplot`, `catplot`, `displot`, `lmplot`): Instantiate and manage a `FacetGrid` figure natively, making multi-categorical column and row faceting seamless.

### 2. Custom Color Theory & Palettes
- **Qualitative**: `colorblind`, `Set2`, `Dark2` (for categorical grouping without implicit order).
- **Sequential**: `mako`, `rocket`, `crest`, `viridis` (for continuous numeric intensity).
- **Diverging**: `coolwarm`, `vlag`, `sns.diverging_palette(h_neg, h_pos)` (for highlighting deviations from a central baseline).

### 3. Seaborn Objects API (`seaborn.objects` / `so.Plot`)
Introduced in Seaborn v0.12+, `so.Plot()` offers a modular grammar of graphics:
```python
import seaborn.objects as so

(
    so.Plot(tips, x="total_bill", y="tip", color="time")
    .add(so.Dot(alpha=0.7))
    .add(so.Line(), so.PolyFit(order=2))
    .label(title="Objects API: Scatter + Order-2 Polynomial Fit")
).show()
```

---

## 📊 Summary of Titanic EDA Key Analytical Findings

1. **Gender Disparity**: Female survival rate was ~74%, compared to ~19% for males ("women and children first" protocol).
2. **Socioeconomic Status**: 1st Class passengers experienced ~63% survival probability versus ~24% for 3rd Class passengers.
3. **Family Dynamics**: Passengers in small family units (2–4 members) achieved higher survival rates compared to single travelers.
4. **Age Priority**: Children (< 12 years old) maintained higher survival rates across all passenger classes.

---

## 📄 License
This repository is open-sourced under the MIT License.