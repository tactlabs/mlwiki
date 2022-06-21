/ [Home](index.md)

# Nesterov Accelerated Gradient

Nesterov Accelerated Gradient(NAG) is an extension of Gradient Descent with momentum(simply momentum) that optimizes the gradient descent algorithm even more.

In Momentum, the learning rate is not dependent on the gradient of the current step, but also on the gradient of the previous step(s). Thus, the value of the step taken by the algorithm accelerates with momentum with each step. As a result, it is possible to overstep the required value, thus having to take steps in the opposite direction to reach the minimum point.

NAG rectifies this by looking ahead of the step to see if it oversteps. First, a partial step is taken to reach the look-ahead point. By using the value of gradient at the look-ahead point, the final value of the step is calculated and taken. This looking ahead helps NAG to converge to the minimum points in fewer steps and reduce the chances of overshooting.

![Nesterov Accelerated Gradient](images/nag.png "Nesterov Accelerated Gradient")

<br>

**Created by Santhosh Kannan**

---

<br>
