/ [Home](../index.md)

# A Visual Approach to Gradient Descent and other Optimization Algorithms

**Note:** Visualize the differences and similarities between gradient descent, gradient descent with momentum, RMSprop, and Adam

*Introduction*

If you are like me, equations do not speak for themselves. To understand them, I need to see what they do with a concrete example. In this blog post, I apply this visualization principle to popular optimization algorithms used in machine learning.

Nowadays, the Adam algorithm is a very popular choice. The Adam algorithm adds momentum and self-tuning of the learning rate to the plain-vanilla gradient descent algorithm. But what are momentum and self-tuning exactly?

Below is a visual preview of what these concepts refer to:
![Optimization Algorigthms](articles/images/101.gif "Optimization Algorigthms")

Linear Regression
To keep things simple, I use different optimization algorithms on the bivariate linear regression model:

y = a + bx

The variable y represents a quantity we try to predict/explain using another variable x. The unknown parameters are the intercept a and the slope b.

To fit the model to the data, we minimize the mean square of the difference between the model and the data, which can be compactly expressed as follows:

```
Loss(a,b)=1/m||y-a-bx||²
```

(assuming we have m observations and using the Euclidean norm)

By changing the value of a and b, we can hopefully improve the fit of the model to the data. With the bivariate regression model, a good thing is that we can plot the value of the loss function as a function of the unknown parameters a and b. Below is a surface plot of the loss function, with the black dot representing the minimum of the loss.

![ABC](articles/images/102.webp "ABC")

We can also visualize the loss function using a contour plot, where the lines are level sets (points such that Loss(a,b) = constant). Below, the white point represents the minimum of the loss function.

![ABC](articles/images/103.webp "ABC")

*Gradient Descent*

The plain-vanilla gradient descent algorithm consists in taking a step of size η in the direction of the steepest descent, which is given by the opposite value of the gradient. Mathematically, the update rule looks like:


In the next plot, I show one trajectory implied by the gradient descent algorithm. Points represent values of a and b across iterations, while arrows are gradients of the loss function, telling us where to move in the next iteration.

A key feature is that the gradient descent algorithm might create some oscillations between level sets. In a perfect world, we would like instead to move smoothly in the direction of the minimum. As we will see, adding momentum is one way to smooth the trajectory toward the minimum value.

![ABC](articles/images/104.gif "ABC")

*Gradient Descent with Momentum*

Momentum refers to the tendency of moving objects to continue moving in the same direction. In practice, we can add momentum to gradient descent by taking into consideration previous values of the gradient. This can be done as follows:

![ABC](articles/images/105.webp "ABC")

The higher the value for γ, the more past values of the gradient are taken into consideration in the current update.

In the next plot, I show the trajectories implied by the gradient descent algorithm with (in blue) and without momentum (in white).

Momentum reduces the fluctuations along the value of the slope coefficient. The big swings up and down tend to cancel out once the averaging effects of momentum start to kick in. As a result, with momentum we move faster in the direction of the true value.

![ABC](articles/images/107.gif "ABC")


*RMSprop*
Momentum is a nice twist to gradient descent. Another line of improvement consists in introducing a learning rate that is tailored to each parameter (in our example: one learning rate for the slope, one learning rate for the intercept).

But how to choose such a coefficient-specific learning rate? Note that the previous plots show that the gradient does not necessarily point toward the minimum. At least not during the first iterations.

Intuitively, we would like to give less weight to the moves in the up/down direction, and more weight to the moves in the left/right direction. The RMSprop updating rule embeds this desired property:

The first line just defines g to the be the gradient of the loss function. The second line says that we calculate a running average of the square of the gradient. In third line, we take a step in the direction given by the gradient, but rescaled by the square root of the running average of past gradients.

In our example, because the square of the gradient tends to be large for the slope coefficient, so we take small steps in that direction. The opposite is true for the intercept coefficient (small values, large moves).

![ABC](articles/images/109.gif "ABC")

*Adams*
The Adam optimization algorithm has momentum, as well as the adaptive learning rate of RMSprop. Below is almost what Adam does:


The updating rule is very similar to one of RMSprop. The key difference is momentum: the direction of change is given by a running average of the past gradient.

The actual Adam updating rule uses “bias-corrected” value for m and v. In the first step, Adam initialize m and v to be zero. To correct for the initialization bias, the authors suggest to use reweighed versions of m and v:

Below, we see that the trajectory induced by Adam is somewhat similar to the one given by RMSprop, but with a slower start.

![ABC](articles/images/112.gif "ABC")

*The master plot*
The next plot shows the trajectories induced by the four optimization algorithms described above.

Key results are as follows:

* Gradient descent with momentum has less fluctuations than gradient descent without momentum.
* Adam and RMSprop take a different route, moving slower in the slope dimension and faster in the intercept dimension.
* As expected, Adam displays some momentum: while RMSprop starts turning left towards the minimum, Adam has a harder time to turn because of the accumulated momentum.

![ABC](articles/images/113.gif "ABC")

Below is the same graph, but in 3d:

![ABC](articles/images/114.gif "ABC")

*Conclusion*
In this blog post, my aim was for the reader to build an intuitive understanding of key optimization algorithms used in machine learning.

Below you can find the code that was used to produce the graphs used in this post. Do not hesitate to modify the learning rate and/or the loss function to see how this affects the different trajectories.

---


*Code (Python)*
The following block of code loads dependencies, defines the loss function and does plots the loss function (surface and contour plots):

