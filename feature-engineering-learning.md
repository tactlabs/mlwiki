/ [Home](index.md)

# Feature Engineering Learning

```
1. Feature Engineering Basics - corporatefinanceinstitute

https://corporatefinanceinstitute.com/resources/knowledge/data-analysis/feature-engineering/

1) feature - variable in dataset(can often be described as a column)

2) why feature engineer?
  - improves the performance of the model by selecting the right features and preparing the features in a way that is suitable for the model.
  - slim down and manipulate features to produce a set of effective predictor variables.
  - Involves questions like(example: car price predictor)
      Is number of seats a good predictor
      Should there be a predictor variable for the shoulder width of every seat?
      Should horsepower and torque be separate predictor variables, or do they provide similar information and only one of them is needed?
  - no single correct method of conducting feature engineering - highly dependent on the dataset and the target variables

3) Steps involved
    - Data Cleansing
    - Data Transformation
    - Feature Extraction
    - Feature Selection
    - Feature Iteration

4) Data Cleansing
    - process of dealing with errors or inconsistencies in the data
    - involves identifying incorrect data, missing data, duplicated data, and irrelevant data
    - process of deleting, replacing, or modifying data to remove outliers and incorrect values.

5) Data Transformation
    - process of transforming the data from one layout to another
    - Transformation needs to occur in a way that does not change the meaning of the original data

Energy:
1. I feel good after reading this article.
2. Topics where written in a clear way and was wasy to understand. Learnt a lot


2. Art of Feature Engineering for Data Science - Nabeel Sarwar

https://www.youtube.com/watch?v=leTyvBPhYzw

1) Feature engineering: Selection, cleaning and transformation & enrich

2) Categorical features:
    - discrete(not necessarily disjoint)
    - can often seem numeric
        distinguish - if process like addition, subtraction, mean lose the meaning of feature - categorical
        eg: id - even though numeric, is a categorical variable - losses meaning when using mean, addition, etc
            material_type(1,2,3,4) - illogical to perform mathematical operations on - Categorical
    - encoding methods: one hot, binary encoding(sometimes better than one hot - memory efficient, increases performance in some models like decision trees)

3) Numerical features:
    - can be continuos or discrete
    - can be http://wiki.tactii.com/feature-engineering-learning.htmlconverted into categorical variable by binning and bucketing
    - should be scaled in case model prioritzes magnitude:
        example: In KNN, if one feature has higher magnitude, it will be prioritized in clustering process as it has the most impact
    - always determine relevant stats: mean, variance, Kurtosis, Mode, Median

4) Cleaning data
    - correcting for input mistakes or known mistakes(normalization)
    - filling missing data - mean, mode, matrix factorization(A = LDU)[advanced]
    - convert data into known formats for rest of pipeline

5) Selecting features
    - Need domain knowledge
    - Use statistically correlate features: weights in linear regression, Gini, Correlation, information Gain(make model with a feature and without feature and check difference), Information criteria(AIC, BIC, Bayes Factors)
    - can't use statistically correlated features for non linear models as they are heavily context dependent(Global gains vs local gains)
    - top-down uproach - Throw all data and sample down
    - bottom-up approach - Throw little data and increase until acceptable toleracne
    - account for noisy or dirty data by understanding the obtaining process

6) Transformation and enrichment
    - Build new features from existing features: add, subtract(from mean), multiply, ratios, polynomials(kernel trick in SVM), Rational difference, (log, sigmoid, exponential transformations), Fourier or Laplace transformation
    - look up tables for aditional features

7) Dimension Reduction
    - Too much features can cause problems in training and deployment
        eg: decision trees have unhealty prunes when using too many features(hence one hot encoding is not optimal for it), slow training
    - Reduce dimension by learning most important "directions" or combination of features - finding the right basis(eigen) vectors
    - Principal Component Analysis - Singular Value Decomposition on covariance matrix
    - Factor Analysis - excpectation-maximization to find basis vectors
    - Non-negative matrix factorization - poisson-gamma factorization

Energy:
1. Really great video. Enjoyed it a lot
2. Undertstood a lot of basic concepts and found new words to google about. Very clear explaination and good examples were given
```

<br>

**Created by Santhosh Kannan**

---

<br>