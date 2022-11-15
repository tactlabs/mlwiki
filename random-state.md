/ [Home](index.md)

# Random State

Random_state is used to set the seed for the random generator so that we can ensure that the results that we get can be reproduced. 

Because of the nature of splitting the data in train and test is randomised you would get different data assigned to the train and test data unless you can control for the random factor.

For example, imagine you have numbers: 1,2,3,4,5 and you want to select two random numbers. 

Without using a random_state you would get different things: i.e. first 2,5 then 3,4 and so on.


When you control the random generator by setting the random state to 0, 1 or another number, everyone would get the same random numbers generated: i.e random_state=1 then the random numbers are 1,3 and everyone who will pick two random numbers using random_state=1 from 1,2,3,4,5 will get the same two numbers as you: 1,3.