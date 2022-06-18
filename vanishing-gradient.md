/ [Home](index.md)

# Vanishing Gradient Problem

Vanishing gradient problem is an issue that may arise in recurrent neural networks and deep learning models that uses gradient-based techniques and backpropagation. It is a problem where the partial derivative used to calculate the gradient is a very small value which gets even smaller with each passing layer, causing it to vanish. Since the value of gradient is used to control the learning rate, if the gradient vanishes, then little to no learning takes place, leading to poor predictive performance.

Solution - Batch normalization, using ReLU activation or Residual Networks

<br>

**Created by Santhosh Kannan**

---

<br>
