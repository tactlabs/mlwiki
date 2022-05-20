/ [Home](index.md)

# Image Masking


In machine learning, masked signal learning is a type of learning where the masked portion of the input is used to learn and predict the masked signal. We can find the use cases of this type of learning in NLP for self-supervised learning.

In the process of blurring we reduce the edge content in an image and try to make the transitions between different pixel intensities as smooth as possible. Noise reduction is also possible with the help of blurring.

Applying masked image modelling can have the following difficulties:

* Pixels near to each other are highly correlated.
* Signals under the images are raw and low level in comparison to the signal (tokens) under the NLP data.
* Signals in image data are continuous while text signals are discrete.

So applying this approach to image or computer vision-related data, requires the procedure to be accomplished very well so that correlation can be avoided. Prediction from the low-level signals can be used for high-level visual tasks and the approach can adapt the continuous signal behaviour. 