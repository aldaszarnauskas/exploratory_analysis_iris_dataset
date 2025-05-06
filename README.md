# Pands-Project

## Table of contents
* [Introduction](#Intro-of-the-project)
* [Analysis](#Exploratory-analysis-on-the-Iris-Dataset)
    * [Import_and_Load](#1-import-required-packages-and-load-and-clean-iris-dataset)
    * [Summary_stats](#2-summary-statistics)
    * [Exploration_of_the_Iris](#3-explonatory-analysis-of-the-iris-dataset)
    * [ANOVA_and_Post-Hoc](#4-difference-between-iris-classess)
* [Requirements](#Requirements)
* [License](#License)
* [Reference](#Reference)

## Intro of the project
![Iris Flower](blue_iris_flower_with_.jpeg)  

This project explores the Iris dataset[^1], a widely used resource in machine learning and statistics[^2]. The dataset comprises 150 samples, with 50 samples each of sepal length, sepal width, petal length, and petal width (in centimeters) for three Iris species: Setosa, Versicolor, and Virginica. (See a beautiful example of an Iris flower above.) The dataset is readily available through Python packages like scikit-learn[^3] and the UC Irvine Machine Learning Repository[^4]. Originally introduced by British statistician Ronald Fisher in his 1936 paper[^5], the data was collected by Edgar Anderson to identify distinct morphologies among different Iris species[^6]. Numerous analyses of the Iris dataset exist online, ranging from exploratory studies of its characteristics[^7] to the application of various machine learning techniques and neural network reconstructions[^8].

In this project, we will conduct an exploratory analysis comparing the three Iris species for each feature to determine if significant differences exist. Establishing such differences would indicate the potential to distinguish these species based on these measurements. Our analysis will begin with summary statistics to understand the dataset's fundamental properties. Subsequently, we will employ histograms and KDE plots for visual exploration of the data distributions. We will then examine the relationships between all feature pairs to observe potential species-based clustering. If differences between Iris species are visually apparent, we will proceed with ANOVA and, if necessary, post-hoc analysis to pinpoint specific significant differences between Iris species. Prior to these statistical tests, we will assess the normality, homogeneity of variances, and independence of the data for each feature, as these are critical assumptions for ANOVA and post-hoc tests and will guide the selection of appropriate statistical methods.



## Exploratory analysis on the Iris Dataset¶
### 1. Import Required Packages and Load and Clean Iris Dataset
In this section, we will load the required packages and the data. Moreover, the DataFrame will undergo a cleaning process to address missing values and remove any redundant information from its columns, ensuring its suitability for further analysis.

#### 1.1 Import required packages
#### 1.2 Load the Iris data set
#### 1.3 Load the metadata of the Iris data set with 'with open()' function
#### 1.4 Extract the attribute information from the metadata file
#### 1.5 Clean the df
### 2. Summary statistics
In this section, we will calculate summary statistics for each feature, including measures of both central tendency and dispersion. There are two main types of measurements for these statistics: absolute and relative. Absolute measurements quantify the actual values within the dataset, allowing us to observe the direct magnitude of these values. In contrast, relative measurements calculate ratios or coefficients that enable comparisons across different datasets, even those with significantly different magnitudes. 

#### 2.1 Calculate summary statistics
#### 2.2 Save summary statistics to a text file
### 3. Explonatory analysis of the Iris dataset
In this section, we will plot histograms, KDE plots, and scatter plots to explore the distribution of each feature and the correlations between feature pairs. This will enhance our understanding of the dataset's features and inform subsequent analyses.

#### 3.1 Initial examination of the datasets, Histogram and KDE plot
#### 3.2 Plot scatter plots of all feature pairs
##### 3.2.1 Calculate $R^{2}$
##### 3.2.2 Plot a regression line on the scatter plot
##### 3.2.3 Define a function to calculate correlation coefficient, r
##### 3.2.4 Define a function to calculate $R^{2}$
#### 3.3 Define a function to plot a regression line
#### 3.4 Plot scatter plots of the features
### 4. Difference Between Iris Classess
ANOVA
In this section, we will examine the differences between three Iris species—Iris setosa, Iris versicolor, and Iris virginica—across four features: sepal length, sepal width, petal length, and petal width. The most suitable method to test for differences between three or more groups for a single dependent variable is ANOVA (Analysis of Variance). Several ANOVA types are suitable for datasets with different properties. For instance, if the dataset has only one independent variable (factor), then a One-Way ANOVA is appropriate. On the other hand, for datasets with two independent variables, a Two-Way ANOVA is the right choice, and for datasets with three or more independent variables, PERMANOVA (Permutational Multivariate Analysis of Variance) is often the optimal choice, especially when dealing with multivariate data. However, ANOVA relies on three key assumptions: the data must be normally distributed, must exhibit homoscedasticity (homogeneous variance), and the data points must be independent. If a dataset does not meet the normality or homoscedasticity assumptions, it can sometimes be transformed to see if these assumptions are met after the transformation. If the dataset still does not meet the assumptions even after data transformations, then we can choose from several ANOVA methods suitable for datasets that do not meet these assumptions. In this case, we will use Welch's ANOVA to test for differences between classes in datasets that violate these assumptions. Furthermore, if the dataset does not meet the independence assumption, then it is not suitable for further analyses and should ideally be resampled.

Normality, Homoscedasticity and Independence
To determine which type of ANOVA we should use, we will assess normality using histograms and QQ-plots of the residuals, homoscedasticity with a residuals versus fitted values plot, and the independence of data points by plotting residuals versus ordered values. In addition to these visual aids, we will further test normality and homoscedasticity using the Shapiro-Wilk test and Levene's test, respectively. If the data meet all the assumptions, then we will use the One-Way ANOVA method. The One-Way ANOVA method is suitable for datasets that meet all assumptions and have only one independent variable; in our case, the independent variable is species. Nonetheless, if the data are not normally distributed or do not have equal variances, we have two options: either transform the data or perform Welch's ANOVA, which is a suitable method for datasets that do not meet the standard ANOVA assumptions. Before deciding to use Welch's ANOVA, we will explore data transformations. There are many ways to transform data, but here we will use five methods: square root, logarithm, squaring, exponential, and reciprocal transformations. If the data meet the assumptions after transformation, then we will use the transformed data with a One-Way ANOVA. However, if none of the transformations successfully allow the data to meet all the assumptions, then we will use Welch's ANOVA. In addition, if the data do not meet the independence criterion, then we either have to collect new samples in a way that ensures independence or include the variable causing the dependence in the statistical model.

Post-Hoc
When the ANOVA model yields a statistically significant result, it indicates that there is a significant difference between at least one pair of the groups being compared. In such cases, a post-hoc test is performed to identify precisely which pairs exhibit this significant difference. Several types of post-hoc tests are available. Ideally, Tukey's Honestly Significant Difference (HSD) test is employed when the data meet both the normality and homoscedasticity assumptions. Conversely, if the data violate these assumptions, the Games-Howell test may be used to determine which specific pairs of groups show a significant difference in their means.

#### 4.1 Visual Examination of Normality, Homogeneity of variance, Independence
#### 4.2 Shapiro-Wilk test and Levene's test
#### 4.3 One Way ANOVA and Welsch's ANOVA
#### 4.4 Post-Hoc TukeyHSD and Games-Howell's Tests
#### 4.5 Box-Plots of the Post-Hoc Results

## Requirements
Find the requirements for this project in [requirements.txt](requirements.txt).


## License
No license

## Reference
[^1]: https://scikit-learn.org/1.4/auto_examples/datasets/plot_iris_dataset.html
[^2]: https://archive.ics.uci.edu/dataset/53/iris
[^3]: https://scikit-learn.org/stable/auto_examples/decomposition/plot_pca_iris.html
[^4]: https://archive.ics.uci.edu/dataset/53/iris
[^5]: https://onlinelibrary.wiley.com/doi/10.1111/j.1469-1809.1936.tb02137.x
[^6]: https://www.kaggle.com/datasets/arshid/iris-flower-dataset
[^7]: https://medium.com/analytics-vidhya/exploratory-data-analysis-iris-dataset-4df6f045cda
[^8]: https://academic.oup.com/jrssig/article/18/6/26/7038520