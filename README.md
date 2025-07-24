# Automobile Price Prediction using Statistical Methods

## Abstract

With the aid of statistical analysis, enormous amounts of data may be gathered, analyzed, and turned into useful information by spotting common patterns and trends. The idea is to employ a dataset on which different statistical techniques can be applied in order to make precise predictions. I try to find out the best suitable model of predicting price of automobiles.

## Introduction

The goal of this project is to put into practice the statistical techniques that were learnt during the Statistical Methods course to analyze actual data. This includes and is not limited to Z-test, Shapiro-Wilk Test, Chi Squared Tests of Independence various distributions, multivariate normality test, categorical analysis of data, Kruskal-Wallis H-test and regression models. To achieve this, we will use the 1985 Ward's Automotive Yearbook dataset. First, I will implement various statistical methods to observe correlations and dependency between the various features of the data, both numerical and categorical. Going ahead, I will be implementing Basic Linear Regression, Forward and Backward elimination methods to select the best features from our data to fit a linear regression model, Principal Component Regression and Polynomial regression. I will test the accuracy of these linear regression models and other parameterized regression models on our test data.

## Methodology

- Shapiro-Wilk Test: It tests the null hypothesis that a sample x1, ..., xn came from a normally distributed population. 
- Z test: A z-test is a statistical test used to determine whether two population means are different when the variances are known and the sample size is large.
- Chi-Square Test: It is a nonparametric independence hypothesis test. We can use it to test whether two categorical variables are related to each other.
- Kruskal-Wallis H-test: The Kruskal–Wallis test by ranks or one-way ANOVA on ranks is a non-parametric method for testing whether samples originate from the same distribution.
- Nemenyni Test: It is a post-hoc test intended to find the groups of data that differ after a global statistical test  has rejected the null hypothesis that the performance of the comparisons on the groups of data is similar. The test makes pair-wise tests of performance.
- Linear Regression: It is a linear approach for modelling the relationship between a scalar response and one or more explanatory variables (also known as dependent and independent variables). The case of one explanatory variable is called simple linear regression; for more than one, the process is called multiple linear regression. This term is distinct from multivariate linear regression, where multiple correlated dependent variables are predicted, rather than a single scalar variable.
- Forward/Backward Sampling: Forward selection starts with model containing null predictions, then add features to the model one at a time, and then predict and compare the performances with each added features, upto the point all the features are into the model. Backward selection starts with the model containing all the features and the performance being compared after taking the least useful feature out one at a time.
- Ridge Regression: Ridge regression is a method of estimating the coefficients of multiple-regression models in scenarios where the independent variables are highly correlated.
- Principal Component Analysis: Principal component analysis (PCA) is a popular technique for analyzing large datasets containing a high number of dimensions/features per observation, increasing the interpretability of data while preserving the maximum amount of information, and enabling the visualization of multidimensional data. Formally, PCA is a statistical technique for reducing the dimensionality of a dataset.
- Polynomial Regression: It is a form of regression analysis in which the relationship between the independent variable x and the dependent variable y is modelled as an nth degree polynomial in x. Polynomial regression fits a nonlinear relationship between the value of x and the corresponding conditional mean of y

## Data Description

Dataset link: <href>https://www.kaggle.com/datasets/toramky/automobile-dataset?resource=download&sort=votes</href>

This dataset consist of data From 1985 Ward's Automotive Yearbook. Here are the sources

Sources:

1. 1985 Model Import Car and Truck Specifications, 1985 Ward's Automotive Yearbook.
2. Personal Auto Manuals, Insurance Services Office, 160 Water Street, New York, NY 10038
3. Insurance Collision Report, Insurance Institute for Highway Safety, Watergate 600, Washington, DC 20037

The Data contains the following columns:

1. symboling: This indicates the risk factor associated with respective car. A value of +3 indicates that the auto is risky, -3 that it is probably pretty safe. 
2. normalized-losses: It is the relative average loss of payment per insured vehicle year. This value is normalized for all autos within a particular size classification (two-door small, station wagons, sports/speciality, etc…), and represents the average loss per car per year.
3. make: It denotes the company that has manufactured the car.
4. fuel-type: It denotes the type of fuel on which the car runs, either gas or diesel.
5. aspiration: It shows the type of internal combustion engine being used in the car. Is it a naturally aspirated engine denoted by "std" or a turbo-charged engine denoted by "turbo".
6. num-of-doors: It shows how many doors does the car have, 2 or 4 doors.
7. body-style: The body style that is followed by the car, e.g: Sedan, Hatchback, etc.
8. drive-wheels: The type of wheel drive used by the car, whether it uses front wheel axel drive, rear wheel drive or 4 wheel drive.
9. engine-location: This determines the placement of engine with respect to the car, either front or back.
10. wheel-base: It is the horizontal distance between the centers of the front and rear wheels.
11. length: The length of the car.
12. width: The width of the car.
13. height: The height of the car.
14. curb-weight: It is the weight of the vehicle including a full tank of fuel and all standard equipment.
15. engine-type: The engine used in the car like overhead camshaft(ohc), dual overhead camshaft(dohc), overhead valve(ohv) etc.
16. num-of-cylinders: The number of cylinders used by the engine of a car.
17. engine-size: It is the volume of fuel and air that can be pushed through a car's cylinders and is measured in cubic centimetres (cc).
18. fuel-system: The method used by which the fuel is stored and supplied to the cylinder chambers.
19. bore: It is the diameter of each cylinder.
20. stroke: The stroke length is how far the piston travels in the cylinder, which is determined by the cranks on the crankshaft.
21. compression-ratio: It is the ratio between the volume of the cylinder and combustion chamber in an internal combustion engine at their maximum and minimum values.
22. horsepower: It is a unit of measurement of power, or the rate at which work is done, usually in reference to the output of engines or motors.
23. peak-rpm: The maximum revolution per minute that can be attained by the car engine.
24. city-mpg: It is the mileage given by the car within city, in miles per gallon.
25. highway-mpg: It is the mileage given by the car on highway, in miles per gallon.
26. price: It is the price of the car.

## Analysis

### Univariate Analysis
**Test to check if the dataset is normally distributed. I also check how likely it is for a random variable in the dataset to be normally distributed.
There are multiple numerical features, I check on all of these features.**

### Comparing two samples
**Statistical Analysis with various hypothesis testing on mulitple paired data types in order to know whether the pair is dependent or indepoendent**

*I perform Z test since the datasets are not normally distributed and the sample size is greater than 30.*

A z-test is a statistical test used to determine whether two population means are different when the variances are known and the sample size is large. If a z-score is 0, it indicates that the data point's score is identical to the mean score. A z-score of 1.0 would indicate a value that is one standard deviation from the mean. Z-scores may be positive or negative, with a positive value indicating the score is above the mean and a negative score indicating it is below the mean. **I use Z test between Numerical & Numerical.**

## Multivariate Normality Test

**I perform the multivariate normality test on the complete data before performing the multivariate analysis.**

### The Analysis of Variance (ONE-WAY ANOVA)

*I perform Kruskal-Wallis H-test for multivariate analysis for more than 2 categorical or numerical data.*

The Kruskal-Wallis H-test tests the null hypothesis that the population mean of all of the groups are equal. It is a non-parametric version of ANOVA. The test works on 2 or more independent samples, which may have different sizes.

*I also perform the Nemenyni Test in order to know which two pairs of data have difference in metrics.*

### The Analysis of Categorical Data

*I perform Chi-Square Test for the independence of different categories of a population.*

The Chi-Square Test computes the chi-square statistic and p-value for the hypothesis test of independence of the observed frequencies in the contingency table observed. The expected frequencies are computed based on the marginal sums under the assumption of independence.

## Linear Regression

I perform initial linear regression followed by various methods to improve and select the best suitable model.

### Resampling Methods

*Forward Selection: It is an iterative method in which I start with having no feature in the model. In each iteration, I keep adding the feature which best improves the model till an addition of a new variable does not improve the performance of the model.*

*Backward Selection: It is an iterative method in which I start with having all the feature in the model. In each iteration, I keep removing the feature which least impact the model till removal of a new variable does not improve the performance of the model.*

### Linear Model Selection and Regularization

*I perform Ridge Regression that uses Linear least squares with l2 regularization. It estimates the coefficients of multiple-regression models in scenarios where the independent variables are highly correlated.*

## Ridge Regression

*I run Ridge Regression on same set of values of alpha as above, on the 15 best feature selected to compare their performance.*

## PCA

*Moving forward, I perform Principal component analysis (PCA) in order to find how many features gather the maximum amount of information and how they perform on the regression model. PCA is a popular technique for analyzing large datasets containing a high number of dimensions/features per observation, increasing the interpretability of data while preserving the maximum amount of information, and enabling the visualization of multidimensional data.*

## Moving beyond Linearity

*I perform poynomial regression, in order to check the model scores compared to just linear regression*

## Conclusion

I have successfully used statistical methods for the analysis of our automotive dataset. I used non-parametric tests to identify the relation (check if their medians are the same) between the numeric input columns and the categorical output columns. Then we did categorical data analysis using the chi-squared test of independence to test the relation between input categorical variables and output categorical variables. I even performed Kruskal-Wallis H-test to compare multiple numerical and categorical data for analysis of variance, followed by Nemenyni Test in order to identify which 2 groups were not following similar distribution.

Further, I ran the basic Linear Regression model in order to predict the price of an automobile on the test split data. I perform various resampling methods, including both forward and backward resampling. I run ridge regression on complete data as well as the best selected features. I perform model selection and regularization in order to fit the best model based on principal component analysis. I even moved beyond linearity by using numerous polynomial degree regression for predicting the price. By implementing all these models and checking for the best result, I come to the conclusion that the best model results were obtained from 15 forward feature selected Linear Regression Model, and it had the best MAPE values on both training and testing dataset.

## References

1. <href>https://www.kaggle.com/datasets/toramky/automobile-dataset?resource=download&sort=votes</href>
2. <href>https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.shapiro.html</href>
3. <href>https://www.statsmodels.org/dev/generated/statsmodels.stats.weightstats.ztest.html</href>
4. <href>https://pingouin-stats.org/generated/pingouin.multivariate_normality.html</href>
5. <href>https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.kruskal.html</href>
6. <href>https://scikit-posthocs.readthedocs.io/en/latest/generated/scikit_posthocs.posthoc_nemenyi/</href>
7. <href>https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.chi2_contingency.html</href>
8. <href>https://scikit-learn.org/0.20/modules/generated/sklearn.linear_model.LinearRegression.html</href>
9. <href>https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.SequentialFeatureSelector.html</href>
10. <href>https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html</href>
11. <href>https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html</href>
12. <href>https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html</href>