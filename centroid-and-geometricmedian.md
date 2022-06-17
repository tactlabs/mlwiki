/ [Home](index.md)

# centroid and geometricmeddian


In clustering algorithms like K-Means there's a commonly quoted example which goes as follows. Imagine there are 5 clusters of people, as a business owner we need to open 5 new food joints in order to cater to these people. K-Means helps us in strategically placing our food joints in such locations so as to reduce the overall time spent by these people to commute to the nearest joint (For simplicity, we're going to ignore the fact that the path between any 2 points in real world is rarely a straight line).

Though this helps us a great deal to wrap our head around the concept of K-Means, it is technically wrong. Centroid minimizes the sum of squares of distances of all the points from it which is not equivalent to minimizing the sum of distances of all the points from it. The point which minimizes the sum of distances of all the points from it is called the geometric median. Centroid (or mean) is very easy to compute, we just have to add all the points (vector addition) and divide it by the number of points whereas there's no simple mathematical formula to find the geometric median there are only numerical methods to find geometric median approximately.

<br>

**Created by Kishore**

---

<br>