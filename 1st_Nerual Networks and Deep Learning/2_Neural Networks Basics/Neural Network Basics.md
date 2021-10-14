# Neural Network Basics

### 1. 질문 1
What does a neuron compute?


1점

A neuron computes a linear function (z = Wx + b) followed by an activation function



A neuron computes a function g that scales the input x linearly (Wx + b)



A neuron computes the mean of all features before applying the output to an activation function



A neuron computes an activation function followed by a linear function (z = Wx + b)



### 2. Which of these is the "Logistic Loss"?
(picture)
### 3.질문 3
Suppose img is a (32,32,3) array, representing a 32x32 image with 3 color channels red, green and blue. How do you reshape this into a column vector?


1점

x = img.reshape((3,32*32))



x = img.reshape((1,32*32,*3))



x = img.reshape((32*32*3,1))



x = img.reshape((32*32,3))



### 4.4.
질문 4
Consider the two following random arrays aa and bb:

 a = np.random.randn(2, 3)a=np.random.randn(2,3) # a.shape = (2, 3)a.shape=(2,3)

b = np.random.randn(2, 1)b=np.random.randn(2,1) #  b.shape = (2, 1)b.shape=(2,1)

c = a + b c=a+b

What will be the shape of cc?


1점

The computation cannot happen because the sizes don't match. It's going to be "Error"!



c.shape = (3, 2)



c.shape = (2, 1)



c.shape = (2, 3)



### 5.5.
질문 5
Consider the two following random arrays aa and bb:

__a = np.random.randn(4, 3)a=np.random.randn(4,3) # a.shape = (4, 3)a.shape=(4,3)__

b = np.random.randn(3, 2)b=np.random.randn(3,2) # b.shape = (3, 2)b.shape=(3,2)

c = a*bc=a∗b 

What will be the shape of cc?


1점

The computation cannot happen because the sizes don't match. It's going to be "Error"!


c.shape = (3, 3)



c.shape = (4,2)



c.shape = (4, 3)



### 6. 	Suppose you have <img src="https://latex.codecogs.com/svg.image?n_{x}" title="n_{x}" /> input features per example. Recall that<img src="https://latex.codecogs.com/svg.image?X&space;=&space;x^{(1)}x^{(2)}...x^{(m)}" title="X = x^{(1)}x^{(2)}...x^{(m)}" />. What is the dimension of X?
- (<img src="https://latex.codecogs.com/svg.image?n_{x}" title="n_{x}" />, m)
### 7.
### 8.
### 9.
### 10.
