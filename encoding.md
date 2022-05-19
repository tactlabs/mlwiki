/ [Home](index.md)

# Encoding

When working on some datasets, we found that some of the features are categorical, if we pass that feature directly to our model, our model can't understand those feature variables. We all know that machines can't understand categorical data. Machines require all independent and dependent variables i.e input and output features to be numeric. This means that if our data contain a categorical variable, we must have to encode it to the numbers before we fit our data to the model.

During Feature Engineering the task of converting categorical features into numerical is called Encoding.
There are various ways to handle categorical features like OneHotEncoding and LabelEncoding, FrequencyEncoding or replacing by categorical features by their count. 