/ [Home](index.md)

# Exploding gradient problem

Exploding gradient problem is an issue that may arise while training artificial neural networks with gradient-based techniques and backpropagation. It is a problem where large error gradients accumulate and result in very large updates to neural networks weights. When there are exploding gradients, an unstable network is formed and the learning cannot be completed. The values of the weights can also become so large as to overflow and result in NaN values.

Solution: gradient clipping and weight regularization

<br>

**Created by Santhosh Kannan**

---

<br>
