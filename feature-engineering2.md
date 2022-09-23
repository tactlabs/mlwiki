/ [Home](index.md)

# Feature Engineering Learning

```
-------------------------------------------------------------------

1. What is Feature Engineering?

https://youtu.be/AnZWCB1gpfE

Notes:

Steps of Feature Engineering:
  1) Data Preprocessing - Algorithm specific
      *Removing outliers
      *Encoded values(categorial value)
      *scaled data

  2)Domain understanding
      *making model understand data better
      *understanding aim of model

3)Makes sure data outcomes isnt biased

4)Converts undefined raw data into a data which the model understands better

5)Model can predict easily because of conversion from raw data to meaningful insights

Energy:
 
1) I was able to learn the basics of Feature Engineering
2) He explained the topic very clearly with examples so it was easy to understand


--------------------------------------------------

2. Outlier detection and removal using IQR | Feature engineering tutorial

https://youtu.be/A3gClkblXK8

Notes:

1) intervals
min to q1(25th percentile): The set of data points between the minimum value and the first quartile.
q1 to q2(50th percentile): The set of data points between the lower quartile and the median.
q3 to q4(75th percentile): The set of data between the median and the upper quartile.
q4 to max: The set of data points between the upper quartile and the maximum value of the data set.

ex: if there are 20 datas- arranged in ascending order
    divide by 5 so 1-5--25th percentile 
    the 1st data ex:1 would be min and 5th data ex: 5.35 would be 25th percentile of the data

2) IQR -Inter Quartile Range 
   
    IQR = Interquartile range = Upper Quartile – Lower Quartile = Q­3 – Q­1

3) To remove outliers:
    
    lower_limit = q1 - 1.5*IQR
    upper_limit = q3 + 1.5*IQR
    upper and lower limit is the max and min value interval 
    other values beyond the interval are outliers

4) df.describe() - gives percentile values
or
   df.col_name.quantile(0.25)

5) Remove the other values ie outliers from data set after calc iqr

Energy:

1) I was able to learn about IQR in detail
2) Learnt a lot of new concepts which were neccesary

----------------------------------------------------------

3.Data Modeling - Feature Engineering

https://youtu.be/rAcZY35aLN4

Notes:

1) Extracting features which are beneficial for model to make it efficient

2) Removing noise -- Nan values filling - replacement by mean
   Outliers removal -- replacement by mean
   encoding
   Binning - grouping data together

3) For categorising data
   df.loc[(df.col_name> condition),'new_col'] = value
   
   ex: df.loc[(df.age> 28.0),'agegroup'] = 1
       df.loc[(df.age< 28.0),'agegroup'] = 0
       This categorises data of age into two categories 0 and 1 

4) After categorising easily outliers can be removed

5) After categorising remove the old columns
   
Energy:

1) I learnt how to categorise the data 
2) I understood the importance of encoding the data

-------------------------------------------------------

4. Feature Engineering Techniques For Machine Learning in Python

https://youtu.be/GduT2ZCc26E

Notes:

1) Dimensionality Reduction (PCA):
    
         Get correlation between similar variables
             If its more than 0.9 means its similar so all of it isnt req for prediction
             ex: no of bedrooms,no of rooms -- they are directly related

  Principal Component Analysis 
    1)unsupervised statistical technique that is used to reduce the dimensions of the dataset
    2)transformation of variables in the dataset into a new set of variables which are called PCs (Principal Components).

    from sklearn.decomposition import PCA 
    pca = PCA(n_components=2)
    #we are converting 3 components into 2
    pca = pca.fit(X_train_3)
    pca

2) Preprocessing/Scaling: (mainly for neural models)
           
         1)StandardScaler lib from sklearn
            Values would be converted in such a way that they are in the closer range
            ex: 2000,34,500 to 0.0614,0.080,-0.2144
            new_value=(old_value-mean)/stdev

         2)Normaliser
         3)MinMaxScaler

note: from sklearn.pipeline import Pipeline 
      new_pipeline = Pipeline(steps=[('Scaler',StandardScaler()),
                                     ('PCA',PCA(n_components=2)),
                                     ('Forest',RandomForestRegressor(n_estimators=50,max_depth=5))])
      this would create a pipeline with steps to know what we Do
      new_pipeline.fit(x_train,y_train) -- this would automatically fit all the three step by step and give us the model

3)Categorical Encoding(Dummy/One-Hot):
         
        pd.get_dummies(c=df['col_name'])
        to categorise a column ino diff cols
        ex: colour col has red green blue
           it makes 3 diff cols red green blue with 0,1 values

4)Binning:
        
        Grouping or aggregating

5)Clustering
        Kmeans - no of components = 3 means it would group into 3 and give an array like (1,0,2,1,0,1,2,1) means they are diff groups
        then do one hot encoding

6)Feature selection:
        Combinations of random  features

Energy:

1) I learnt different steps in feature engineering
2) Makes me wanna try implementing more of these features in my tasks

-------------------------------------------------------

5. Feature Engineering Secret From A Kaggle Grandmaster

https://youtu.be/ft77eXtn30Q

Notes:

1)aggregating-- similar to groupby
             --categorial cols
             --one hot encoding

2)Time series feature engineering 
            time - Ordinal variables
            then groupby
            (rolling,lag,difference,date components)
            time - season,duration

3)entrophy,mean duration,median duration

4)Filtering

5)featuretools-- lib having automated aggregations

6)graphs-- networking
          aggregating in an other level

https://featuretools.alteryx.com/en/stable/getting_started/primitives.html


Energy:

1) Learnt the diff methods of aggregations
2) Came across new tools
-------------------------------------------------------

6. How to use Feature Engineering for Machine Learning, Equations

https://youtu.be/X4pWmkxEikM

Notes:

1)Normalise -- divide

2)Combine -- add or subtract

3)Scaler -- in a range

4)Contrast -- absolute or modulus values

5) Do all these steps and make it a single col and combine as a feature in df

Energy:

1) I learnt the building blocks of feature engineering
2) Got a new perspective of looking at the data

-------------------------------------------------------

7. Intro to Feature Engineering with TensorFlow - Machine Learning Recipes

https://youtu.be/d12ra3b_M-0

1) Facets tool - visualise : https://goo.gl/Dfpb7W

2) Bucketing : Different weights for each bucket(ranges)

3)Categorical and Feature Crossing : Combining 2 or 3 features into one

4)Hashed Columns : Save memory and time
                   limit max no of categories

5)Embedding: large vocabulary, for concepts

TensorFlow Embedding Projector: https://goo.gl/2SxrYK -- new data

Energy:

1) I learnt new tools of feature engineering
2) Visualising methods were understood

-------------------------------------------------------
```

<br>

**Created by Snekha S**

---

<br>