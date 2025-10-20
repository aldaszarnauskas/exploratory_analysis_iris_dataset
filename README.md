# Exploratory Analysis of the Iris Dataset

### Author  
**Aldas Zarnauskas**

---

## Table of Contents
- [Introduction](#introduction)
- [Exploratory Analysis](#exploratory-analysis)
  - [1. Import, Load, and Clean Data](#1-import-load-and-clean-data)
  - [2. Summary Statistics](#2-summary-statistics)
  - [3. Exploratory Data Analysis](#3-exploratory-data-analysis)
  - [4. ANOVA and Post-Hoc Analysis](#4-anova-and-post-hoc-analysis)
- [Requirements](#requirements)
- [License](#license)
- [References](#references)

---

## Introduction
<img src="blue_iris_flower_with_.jpeg" alt="Iris Flower" width="350">

This project explores the **Iris dataset**[^1], a classic resource in **machine learning and statistics**[^2].  
The dataset contains **150 samples** of three Iris species—*Setosa*, *Versicolor*, and *Virginica*—each with **50 samples**.  
Each sample includes four numerical features:

- Sepal length  
- Sepal width  
- Petal length  
- Petal width  

These measurements (in centimeters) are used to distinguish among the species.

The dataset is available through **scikit-learn**[^3] and the **UC Irvine Machine Learning Repository**[^4].  
Originally introduced by *Ronald Fisher (1936)*[^5] and collected by *Edgar Anderson*[^6], it has since become a foundational dataset for testing classification and statistical analysis techniques[^7] [^8].

### Project Aim
In this project, we perform an **exploratory data analysis (EDA)** to determine whether significant differences exist among the three Iris species based on their features.

We begin with:
- **Summary statistics** to understand basic data properties.  
- **Visual exploration** using histograms, KDE plots, and scatter plots to identify clustering patterns.  
- **Statistical tests** (ANOVA and post-hoc analyses) to confirm whether observed differences are statistically significant.  

All analyses are conducted in the notebook [pands-project.ipynb](pands-project.ipynb).  
Generated figures (`.png`) and tables (`.txt`) are available in this repository.

---

## Exploratory Analysis

### 1. Import, Load, and Clean Data
In this section, we:
- Import required Python packages.
- Load the Iris dataset.
- Read metadata using the `with open()` function.
- Extract attribute information.
- Clean the dataset by handling missing values and removing redundant columns.

---

### 2. Summary Statistics
We calculate **summary statistics** for each feature, including measures of **central tendency** and **dispersion**.

Two types of metrics are considered:
- **Absolute measures** – quantify actual values (e.g., mean, median, std).
- **Relative measures** – express relationships (e.g., coefficients of variation).

#### Steps
- 2.1 Compute summary statistics  
- 2.2 Save statistics to a text file  

---

### 3. Exploratory Data Analysis
We visualize distributions and relationships between features.

#### Methods
- **Histograms and KDE plots** – visualize feature distributions by species.  
- **Scatter plots** – examine pairwise relationships between features.  
- **Regression analysis** – calculate correlation coefficients (`r`) and coefficients of determination (`R²`).  

#### Steps
- 3.1 Plot histograms and KDEs  
- 3.2 Plot scatter matrices and regression lines  
- 3.3 Define helper functions for `r` and `R²`  
- 3.4 Save generated plots as `.png` files  

---

### 4. ANOVA and Post-Hoc Analysis

We test for differences among Iris species using **ANOVA (Analysis of Variance)** and **post-hoc** methods.

#### 4.1 Testing Assumptions
Before performing ANOVA, we check three assumptions:
- **Normality** (via histograms, QQ-plots, and Shapiro–Wilk test)
- **Homogeneity of variances** (via residual plots and Levene’s test)
- **Independence** (via residual vs. ordered values plots)

If assumptions are violated:
- We attempt **data transformations** (square root, log, square, exponential, reciprocal).
- If violations persist, we apply **Welch’s ANOVA**, suitable for unequal variances.

#### 4.2 Post-Hoc Analysis
When ANOVA reveals significant differences:
- **Tukey’s HSD test** is used if assumptions are met.  
- **Games–Howell test** is used if assumptions are violated.

#### 4.3 Visualization
Final results are presented using **box plots** of post-hoc comparisons.

---

## Requirements
All dependencies are listed in [requirements.txt](requirements.txt).  
To install them, run:

```bash
pip install -r requirements.txt
```

## License
No license specified.

## Reference
[^1]: https://scikit-learn.org/1.4/auto_examples/datasets/plot_iris_dataset.html
[^2]: https://archive.ics.uci.edu/dataset/53/iris
[^3]: https://scikit-learn.org/stable/auto_examples/decomposition/plot_pca_iris.html
[^4]: https://archive.ics.uci.edu/dataset/53/iris
[^5]: https://onlinelibrary.wiley.com/doi/10.1111/j.1469-1809.1936.tb02137.x
[^6]: https://www.kaggle.com/datasets/arshid/iris-flower-dataset
[^7]: https://medium.com/analytics-vidhya/exploratory-data-analysis-iris-dataset-4df6f045cda
[^8]: https://academic.oup.com/jrssig/article/18/6/26/7038520