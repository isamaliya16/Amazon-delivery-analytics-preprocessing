<div align="center">

<!-- Animated Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Amazon%20Delivery%20Analytics&fontSize=40&fontColor=fff&animation=fadeIn&fontAlignY=38&desc=Last-Mile%20Preprocessing%20Pipeline&descAlignY=58&descAlign=50&descSize=18" width="100%"/>

<br/>

<!-- Badges Row 1 -->
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-1.3+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![NumPy](https://img.shields.io/badge/NumPy-1.24+-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org)

<!-- Badges Row 2 -->
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white)]()
[![Tasks](https://img.shields.io/badge/Tasks-11%20Completed-FF9900?style=for-the-badge&logo=amazon&logoColor=white)]()
[![Records](https://img.shields.io/badge/Records-50%2C000+-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)]()

<br/>

```
╔═══════════════════════════════════════════════════════════════════╗
║   🚚  Preprocessing · EDA · Feature Engineering · ML Pipeline   ║
║         Amazon India Logistics Intelligence · 2025–2026          ║
╚═══════════════════════════════════════════════════════════════════╝
```

</div>

---

## 📖 Overview

> **A production-grade, end-to-end data preprocessing and feature engineering pipeline** built for Amazon India's Last-Mile Delivery Analytics system — transforming raw, messy logistics data into a clean, model-ready dataset for **ETA prediction** and **delay classification**.

This pipeline covers every stage of the data science workflow — from initial loading and cleaning, through advanced imputation and outlier treatment, all the way to a fully modular **`ColumnTransformer` sklearn Pipeline** with zero data leakage.

---

## 🗂️ Dataset Overview

<div align="center">

| 📦 Dataset | 📄 File | 📊 Records | 🔢 Features |
|---|---|---|---|
| **Primary — Delivery Orders** | `amazon_deliveries.csv` | 50,000+ rows | 12 columns |
| **Secondary — Agent Profiles** | `amazon_agents.json` | 6,000 records | 6 fields |
| **Merged & Cleaned Output** | `amazon_deliveries_cleaned.csv` | 50,000 rows | 18 columns |
| **ML-Ready Final Output** | `amazon_deliveries_processed.csv` | 50,000 rows | 34+ features |

</div>

---

## ✨ Features at a Glance

```
🔍 Data Understanding    →   📋 Quality Reports + Missing Value Heatmaps
🧹 Data Cleaning         →   Imputation · Deduplication · Standardization
📊 EDA                   →   Univariate · Bivariate · Multivariate Analysis
💉 Advanced Imputation   →   SimpleImputer vs KNNImputer Comparison
🎯 Outlier Handling      →   Z-Score · IQR · Percentile · Winsorization
⚙️  Feature Engineering  →   Datetime · Business · Log/Sqrt Transforms
🔡 Encoding              →   Label · One-Hot · Ordinal Encoding
📐 Scaling               →   Standard · MinMax · MaxAbs · Robust
🔧 Final Pipeline        →   ColumnTransformer · No Data Leakage
```

---

## 🔬 11-Task Pipeline Breakdown

| # | Task | Description |
|---|---|---|
| 🔍 01 | **Data Understanding & Loading** | Both datasets are loaded and merged into a single unified table. We inspect column types, count unique values, compute basic statistics, and visualize missing data patterns using a heatmap to understand the overall data quality. |
| 🧹 02 | **Data Cleaning** | Missing values are filled using appropriate strategies — median for distances, mean for ratings, and mode for weather. Duplicate orders are removed, city and vehicle names are standardised to consistent casing, and unrealistic delivery times or weights are flagged and corrected. |
| 📊 03 | **Exploratory Data Analysis** | The data is analysed at three levels — individual features (distributions, skewness), pairs of features (how distance and traffic affect delivery time), and combined effects (city vs weather vs delay rate). Key business insights such as high-delay cities and peak-hour patterns are documented. |
| 💉 04 | **Advanced Missing Value Treatment** | Two imputation strategies are compared side by side — a simple fill using column statistics, and a smarter KNN-based approach that looks at similar records to estimate missing values. Distribution plots show which method better preserves the original data shape. |
| 🎯 05 | **Outlier Detection & Handling** | Extreme values are detected using three methods — Z-Score, IQR range checks, and percentile capping. Winsorization is then applied to bring outliers within acceptable bounds without deleting records. Before-and-after statistics confirm the improvement. |
| ⚙️ 06 | **Feature Engineering** | New meaningful columns are created from existing data — time-of-day flags (peak hour, night delivery), distance bands (short/medium/long), agent seniority levels, and log/square-root transforms to reduce skewness in numerical columns. |
| 🔀 07 | **Mixed & Special Variable Handling** | All columns are categorised by type (numerical, categorical, datetime, binary). Agent tenure in days is calculated from their joining date, useful date parts are extracted from the order ID, and raw ID and date columns are dropped so only clean model-ready features remain. |
| 🔡 08 | **Encoding Categorical Data** | Text categories are converted to numbers that machine learning models can understand. Ordered categories like delivery zone and traffic severity use ordinal encoding, while unordered ones like city and weather use one-hot encoding to avoid implying any false ranking. |
| 📐 09 | **Binning & Discretization** | Continuous numbers are grouped into meaningful buckets — for example, delivery time split into Very Short, Short, Medium, Long, and Very Long. Three binning strategies (equal-width, equal-frequency, and cluster-based) are compared for balance and usefulness. |
| 📏 10 | **Feature Scaling** | Four scaling methods are applied and compared — Standard, MinMax, MaxAbs, and Robust. RobustScaler is recommended for this dataset as it handles outliers well. A strict train/test split ensures no information from test data influences the scaling. |
| 🔧 11 | **Final ColumnTransformer Pipeline** | All preprocessing steps are assembled into a single, reusable sklearn pipeline. Numerical features go through imputation, power transformation, and robust scaling. Categorical features go through imputation and encoding. The pipeline is fitted on training data only, guaranteeing zero data leakage. |

---

## 📦 Tech Stack

<div align="center">

| 🛠️ Library | 🔖 Version | 🎯 Purpose |
|---|---|---|
| `pandas` | 2.0+ | Data loading, cleaning, transformation |
| `numpy` | 1.24+ | Numerical operations |
| `scikit-learn` | 1.3+ | Imputers, encoders, scalers, Pipeline |
| `matplotlib` | 3.7+ | Base plotting |
| `seaborn` | 0.12+ | Statistical visualizations |
| `scipy` | 1.11+ | Z-score, Winsorization |
| `ydata-profiling` | 4.0+ | Automated EDA report |

</div>

---

## 📈 Key Results & Insights

```
📍 50,000 delivery records processed across 16 Indian cities
📍 National average delay rate         →  50.22%
📍 Highest delay cities                →  Patna (51.8%), Lucknow (51.2%), Delhi (50.9%)
📍 Skewness after log transform        →  delivery_time_min: 2.007 → 0.026
📍 KNN vs SimpleImputer                →  KNN preserves spatial correlation better
📍 Best scaler for this dataset        →  RobustScaler (outlier-resilient)
📍 Final ML-ready feature count        →  63 features (from original 12)
```

---

## ⚡ Advantages

- 🔁 **Fully Reproducible** — `random_state=42` seeded throughout
- 🧱 **Modular Design** — each task is an independent, reusable block
- 🛡️ **Zero Data Leakage** — all scalers/imputers fitted on train split only
- 📊 **Comprehensive EDA** — 9 visualisation outputs saved automatically
- 🔌 **Pipeline-Ready** — drop the `ColumnTransformer` into any sklearn workflow
- 📋 **Well-Documented** — every step prints a human-readable summary log
- ⚙️ **Scalable** — tested on 50,000 rows; structure scales to millions

---

## 📊 Evaluation Criteria Coverage

<div align="center">

| Criterion | Weight | Status |
|---|---|---|
| 🧹 Data Cleaning Effectiveness | 20% | ✅ Complete |
| 📊 EDA Depth & Insights | 20% | ✅ Complete |
| ⚙️ Preprocessing Technique Accuracy | 25% | ✅ Complete |
| 🔧 Feature Engineering Quality | 15% | ✅ Complete |
| 🔌 Pipeline Design | 10% | ✅ Complete |
| 📝 Code Readability | 10% | ✅ Complete |

</div>

---

## 👤 Author

<div align="center">

**Built for Amazon Logistics Intelligence · Data Analytics Division**  
*Academic Simulation Project — Synthetic Dataset*

---

⭐ **Star this repo** if you found it useful!

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>
