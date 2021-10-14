# Key Concepts on Deep Neural Networks

### 1. What is the "cache" used for in our implementation of forward propagation and backward propagation?
- [ ] It is used to keep track of the hyperparameters that we are searching over, to speed up computation.
- [ ] It is used to cache the intermediate values of the cost function during training.
- [ ] We use it to pass variables computed during backward propagation to the corresponding forward propagation step. It contains useful values for forward propagation to compute activations.
- [x] We use it to pass variables computed during forward propagation to the corresponding backward propagation step. It contains useful values for backward propagation to compute derivatives.

### 2. Among the following, which ones are "hyperparameters"? (Check all that apply.)
- [ ] activation values <img src="https://latex.codecogs.com/svg.image?a^{[l]}" title="a^{[l]}" />
- [ ] weight matrices <img src="https://latex.codecogs.com/svg.image?W^{[l]}" title="W^{[l]}" />
- [ ] bias vectors <img src="https://latex.codecogs.com/svg.image?b^{[l]}" title="b^{[l]}" />
- [x] size of the hidden layers <img src="https://latex.codecogs.com/svg.image?n^{[l]}" title="n^{[l]}" />
- [x] number of iterations
- [x] number of layers <img src="https://latex.codecogs.com/svg.image?L" title="L" /> in the neural network
- [x] learning rate <img src="https://latex.codecogs.com/svg.image?\alpha" title="\alpha" />

### 3. Which of the following statements is true?
- [x] The deeper layers of a neural network are typically computing more complex features of the input than the earlier layers.
- [ ] The earlier layers of a neural network are typically computing more complex features of the input than the deeper layers.

### 4. Vectorization allows you to compute forward propagation in an LL-layer neural network without an explicit for-loop (or any other explicit iterative loop) over the layers l=1, 2, …,L. True/False?
- False
> Forward propagation propagates the input through the layers, although for shallow networks we may just write all the lines <img src="https://latex.codecogs.com/svg.image?(a^{[2]}&space;=&space;g^{[2]}(z^{[2]}),z^{[2]}=&space;W^{[2]}a^{[1]}&space;b^{[2]}...)" title="(a^{[2]} = g^{[2]}(z^{[2]}),z^{[2]}= W^{[2]}a^{[1]} b^{[2]}...)" /> in a deeper network, we cannot avoid a for loop iterating over the layers: <img src="https://latex.codecogs.com/svg.image?(a^{[l]}&space;=&space;g^{[l]}(z^{[l]}),z^{[l]}=&space;W^{[l]}a^{[l-1]}&space;b^{[l]}...)" title="(a^{[l]} = g^{[l]}(z^{[l]}),z^{[l]}= W^{[l]}a^{[l-1]} b^{[l]}...)" /> 

### 5. Assume we store the values for <img src="https://latex.codecogs.com/svg.image?n^{[l]}" title="n^{[l]}" /> in an array called layer_dims, as follows: <img src="https://latex.codecogs.com/svg.image?layer\_dims&space;=&space;[n_{x},4,3,2,1]" title="layer\_dims = [n_{x},4,3,2,1]" />. So layer 1 has four hidden units, , layer 2 has 3 hidden units and so on. Which of the following for-loops will allow you to initialize the parameters for the model?

    for i in range(1, len(layer_dims)):
        parameter['W' + str(i)] = np.random.randn(layer_dims[i], layer_dims[i-1]) * 0.01
        parameter['b' + str(i)] = np.random.randn(layer_dims[i], 1) * 0.01  

### 6. Consider the following neural network.
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/1st_Nerual%20Networks%20and%20Deep%20Learning/4_Deep%20Neural%20Networks/C1W4_Q_image/6.png">
</p>

How many layers does this network have?

- The number of Layers L is 4. The number of hidden layer is 3.

### 7.During forward propagation, in the forward function for a layer <img src="https://latex.codecogs.com/svg.image?l" title="l" /> you need to know what is the activation function in a layer (Sigmoid, tanh, ReLU, etc.). During backpropagation, the corresponding backward function also needs to know what is the activation function for layer <img src="https://latex.codecogs.com/svg.image?l" title="l" />, since the gradient depends on it. True/False?
- Ture

### 8. There are certain functions with the following properties:
(i) To compute the function using a shallow network circuit, you will need a large network (where we measure size by the number of logic gates in the network), but (ii) To compute it using a deep network circuit, you need only an exponentially smaller network. True/False?
- True

### 9. Consider the following 2 hidden layer neural network:
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/1st_Nerual%20Networks%20and%20Deep%20Learning/4_Deep%20Neural%20Networks/C1W4_Q_image/9.png">
</p>
Which of the following statements are True? (Check all that apply).

- [ ] <img src="https://latex.codecogs.com/svg.image?b^{[3]}" title="b^{[3]}" /> will have shape (3, 1)
- [ ] <img src="https://latex.codecogs.com/svg.image?b^{[1]}" title="b^{[1]}" /> will have shape (3, 1)
- [ ] <img src="https://latex.codecogs.com/svg.image?W^{[2]}" title="W^{[2]}" /> will have shape (3, 1)
- [x] <img src="https://latex.codecogs.com/svg.image?b^{[3]}" title="b^{[3]}" /> will have shape (1, 1)
- [x] <img src="https://latex.codecogs.com/svg.image?W^{[3]}" title="W^{[3]}" /> will have shape (1, 3)
- [ ] <img src="https://latex.codecogs.com/svg.image?W^{[1]}" title="W^{[1]}" /> will have shape (3, 4)
- [x] <img src="https://latex.codecogs.com/svg.image?b^{[1]}" title="b^{[1]}" /> will have shape (4, 1)
- [ ] <img src="https://latex.codecogs.com/svg.image?b^{[2]}" title="b^{[2]}" /> will have shape (1, 1)
- [x] <img src="https://latex.codecogs.com/svg.image?W^{[1]}" title="W^{[1]}" /> will have shape (4, 4)
- [ ] <img src="https://latex.codecogs.com/svg.image?W^{[3]}" title="W^{[3]}" /> will have shape (3, 1)
- [x] <img src="https://latex.codecogs.com/svg.image?b^{[2]}" title="b^{[2]}" /> will have shape (3, 1)
- [x] <img src="https://latex.codecogs.com/svg.image?W^{[2]}" title="W^{[2]}" /> will have shape (3, 4)

> More generally   ,
> <img src="https://latex.codecogs.com/svg.image?b^{[l]}&space;\&space;is&space;\&space;(n^{[l]},&space;1)" title="b^{[l]} \ is \ (n^{[l]}, 1)" />   
> <img src="https://latex.codecogs.com/svg.image?W^{[l]}&space;\&space;is&space;\&space;(n^{[l]},&space;n^{[l-1]})" title="W^{[l]} \ is \ (n^{[l]}, n^{[l-1]})" />

### 10. Whereas the previous question used a specific network, in the general case what is the dimension of <img src="https://latex.codecogs.com/svg.image?W^{[l]}" title="W^{[l]}" />, the weight matrix associated with layer <img src="https://latex.codecogs.com/svg.image?l" title="l" />?
- <img src="https://latex.codecogs.com/svg.image?W^{[l]}&space;\&space;has&space;\&space;shape&space;\&space;(n^{[l]}),&space;n^{[l-l]}" title="W^{[l]} \ has \ shape \ (n^{[l]}), n^{[l-l]}" />