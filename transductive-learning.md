/ [Home](index.md)

# Transductive Learning

Transduction is reasoning from observed, specific (training) cases to specific (test) cases. Transductive learning techniques have observed all the data beforehand, both the training and testing datasets. We learn from the already observed training dataset and then predict the labels of the testing dataset. Even though we do not know the labels of the testing datasets, we can make use of the patterns and additional information present in this data during the learning process. Transductive learning can become costly in the case where new data points are introduced by an input stream. Each time a new data point arrives, you will have to re-run everything. 