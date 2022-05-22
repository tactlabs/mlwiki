/ [Home](index.md)

# Variance

Variance is the very opposite of Bias. During training, it allows our model to ‘see’ the data a certain number of times to find patterns in it. If it does not work on the data for long enough, it will not find patterns and bias occurs. And if our model is allowed to view the data too many times, it will learn very well for only that data. It will capture most patterns in the data,  but it will also learn from the unnecessary data present, or from the noise. 
We can define variance as the model’s sensitivity to fluctuations in the data.


Fixing High Variance
* Reduce the input features, use only features with more feature importance to reduce overfitting the data.
* Getting more training data will help in this case, because the high variance model will not be working for an independent dataset if you have very data.

<br>

![Bias](images/bias_variance.jpeg "Bias")

<br>

