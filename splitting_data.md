/ [Home](index.md)

# Splitting Data

Ethically, it is suggested to divide your dataset into three parts to avoid overfitting and model selection bias called -

* Training set (Has to be the largest set)
* Cross-Validation set or Development set or Dev set
* Testing Set

## Training Set:
The sample of data used to fit the model, that is the actual subset of the dataset that we use to train the model (estimating the weights and biases in the case of Neural Network). The model observes and learns from this data and optimize its parameters.

## Cross-Validation Set:
A development set is the data you would use to optimize your model against during the development process. Development set is just another name for validation set, which is used to tune the parameters of your training algorithm and in a way guide it prevent over-fitting

## Test set:
The sample of data used to provide an unbiased evaluation of a final model fit on the training dataset. It is only used once the model is completely trained using the training and validation sets. Therefore test set is the one used to replicate the type of situation that will be encountered once the model is deployed for real-time use.