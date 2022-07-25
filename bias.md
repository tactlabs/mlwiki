/ [Home](index.md)

# Bias

<br>

![Bias](images/bias_variance.jpeg "Bias")

<br>

The bias will express how well a certain machine learning model fits a particular dataset. The bias of a specific machine learning model trained on a specific dataset describes how well this machine learning model can capture the relationship between the features and the targets.

* large training error -> large bias
* small training error -> small bias

When the Bias is high, assumptions made by our model are too basic, the model can’t capture the important features of our data. This means that our model hasn’t captured patterns in the training data and hence cannot perform well on the testing data too.

<br>

![Bias](images/bias.png "Bias")

<br>

Fixing High Bias
* Adding more input features will help improve the data to fit better.
* Add more polynomial features to improve the complexity of the model.
* Decrease the regularization term to have a balance between bias and variance.


<hr/>

Version:2
Author:Raji

As we know,humans show bias in certain things.But machines don't and should not.So,we should check our model whether it shows bias.There are examples where it has showed bias.For instance,amazon built a modelt to filter good candidates from a bunch who applied for the position.Apparently,it showed bias by preferring men over women because the data that we gave for training and testing has resume of people who worked there for the past 10 years.As the number of male employees are more comparing to women,the model became biased.

The bias may be related to source of data,contents of data and training of the model.

There are many tools developed by various comapnies to solve bias.

Google's What-If tool

It has the optimization strategy and checks how balanced the data wit which we can find whelther it is biased or not

IBM AI Fairness 360

It has more than 70 fairness metrics and 10 bias mitigation algorithms which helps us to detect bias and remove it. Bias mitigation algorithms include optimized preprocessing, re-weighting, prejudice remover regularizer, and others. Metrics include Euclidean and Manhattan distance, statistical parity difference, and many others.

