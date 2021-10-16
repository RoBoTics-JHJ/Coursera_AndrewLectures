# Shallow Neural Networks

### 1. Which of the following are true? (Check all that apply.)
- <img src="https://latex.codecogs.com/svg.image?a_4{^{[2]}}" title="a_4{^{[2]}}" /> is the activation output by the <img src="https://latex.codecogs.com/svg.image?4^{th}" title="4^{th}" /> neuron of the <img src="https://latex.codecogs.com/svg.image?2^{nd}" title="2^{nd}" /> layer
- **X** is a matrix in which each column is one training example.
- <img src="https://latex.codecogs.com/svg.image?a^{[2](12)}" title="a^{[2](12)}" /> denotes the activation vector of the <img src="https://latex.codecogs.com/svg.image?2^{nd}" title="2^{nd}" /> layer for the <img src="https://latex.codecogs.com/svg.image?12^{th}" title="12^{th}" /> training example.
- <img src="https://latex.codecogs.com/svg.image?a^{[2]}" title="a^{[2]}" /> denotes the activation vector of the <img src="https://latex.codecogs.com/svg.image?2^{nd}" title="2^{nd}" /> layer.

### 2. The tanh activation is not always better than sigmoid activation function for hidden units because the mean of its output is closer to zero, and so it centers the data, making learning complex for the next layer. True/False?
- False

### 3. Which of these is a correct vectorized implementation of forward propagation for layer <img src="https://latex.codecogs.com/svg.image?l" title="l" />, where  ?
- <img src="https://latex.codecogs.com/svg.image?Z^{[l]}&space;=&space;W^{[l]}A^{[l-1]}&space;&plus;&space;b^{[l]}" title="Z^{[l]} = W^{[l]}A^{[l-1]} + b^{[l]}" />
- <img src="https://latex.codecogs.com/svg.image?A^{[l]}&space;=&space;g^{[l]}(Z^{[l]})" title="A^{[l]} = g^{[l]}(Z^{[l]})" />

### 4. You are building a binary classifier for recognizing cucumbers (y=1) vs. watermelons (y=0). Which one of these activation functions would you recommend using for the output layer? 
- sigmoid
> Sigmoid outputs a value between 0 and 1 which makes it a very good choice for binary classification. You can classify as 0 if the output is less than 0.5 and classify as 1 if the output is more than 0.5. It can be done with tanh as well but it is less convenient as the output is between -1 and 1.


### 5. Consider the following code:
    A = np.random.randn(4,3)B = np.sum(A, axis = 1, keepdims = True) 
What will be B.shape? (If you’re not sure, feel free to run this in python to find out).
- (4,1)
> we use (keepdims = True) to make sure that A.shape is (4,1) and not (4, ). It makes our code more robust. 

### 6. Suppose you have built a neural network. You decide to initialize the weights and biases to be zero. Which of the following statements is true?
- Each neuron in the first hidden layer will perform the same computation. So even after multiple iterations of gradient descent each neuron in the layer will be computing the same thing as other neurons. 

### 7. Logistic regression’s weights w should be initialized randomly rather than to all zeros, because if you initialize to all zeros, then logistic regression will fail to learn a useful decision boundary because it will fail to “break symmetry”, True/False?
- False
>  Logistic Regression doesn't have a hidden layer. If you initialize the weights to zeros, the first example x fed in the logistic regression will output zero but the derivatives of the Logistic Regression depend on the input x (because there's no hidden layer) which is not zero. So at the second iteration, the weights values follow x's distribution and are different from each other if x is not a constant vector. 

### 8. You have built a network using the tanh activation for all the hidden units. You initialize the weights to relative large values, using np.random.randn(..,..)*1000. What will happen? 
- This will cause the inputs of the tanh to also be very large, thus causing gradients to be close to zero. The optimization algorithm will thus become slow. 

> tanh becomes flat for large values, this leads its gradient to be close to zero. This slows down the optimization algorithm.

### 9. Consider the following 1 hidden layer neural network:
<p align="center">
  <img width="40%" height="30%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/1st_Nerual%20Networks%20and%20Deep%20Learning/3_Shallow%20neural%20networks/C1W3_Q_image/9.png">
</p>

- <img src="https://latex.codecogs.com/svg.image?W^{[2]}" title="W^{[2]}" /> will have shape (1, 4)
- <img src="https://latex.codecogs.com/svg.image?b^{[1]}" title="b^{[1]}" /> will have shape (4, 1)
- <img src="https://latex.codecogs.com/svg.image?W^{[1]}" title="W^{[1]}" /> will have shape (4, 2)
- <img src="https://latex.codecogs.com/svg.image?b^{[2]}" title="b^{[2]}" /> will have shape (1, 1)

### 10. In the same network as the previous question, what are the dimensions of <img src="https://latex.codecogs.com/svg.image?Z^{[l]}" title="Z^{[l]}" /> and <img src="https://latex.codecogs.com/svg.image?A^{[l]}" title="A^{[l]}" />? 
- <img src="https://latex.codecogs.com/svg.image?Z^{[l]}" title="Z^{[l]}" /> and <img src="https://latex.codecogs.com/svg.image?A^{[l]}" title="A^{[l]}" /> are (4, m)