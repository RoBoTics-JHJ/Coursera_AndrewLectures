# The Basics of ConvNets

### 1. What do you think applying this filter to a grayscale image will do?
<img src="https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;0&&space;&space;1&&space;&space;-1&&space;&space;0\\&space;1&&space;&space;3&&space;&space;-3&&space;&space;-1\\&space;1&&space;&space;3&&space;&space;-3&&space;&space;-1\\&space;0&&space;&space;1&&space;&space;-1&&space;&space;0\\\end{bmatrix}" title="\begin{bmatrix} 0& 1& -1& 0\\ 1& 3& -3& -1\\ 1& 3& -3& -1\\ 0& 1& -1& 0\\\end{bmatrix}" />

- [x] Detect vertical edges
- [ ] Detect horizontal edges
- [ ] Detect image contrast
- [ ] Detect 45 degree edges
> As you can see the difference between values from the left part and values from the right of this filter is high. When convolving this filter on a grayscale image, the vertical edges will be detected.
---

### 2. Suppose your input is a 300 by 300 color (RGB) image, and you are not using a convolutional network. If the first hidden layer has 100 neurons, each one fully connected to the input, how many parameters does this hidden layer have (including the bias parameters)?
- [x] 27,000,100
- [ ] 9,000,100
- [ ] 27,000,001
- [ ] 9,000,001
> the number of weights is 300×300×3×100=27,000,000, when you add the bias terms (one per neurons) you get 27,000,100.
---

### 3. Suppose your input is a 300 by 300 color (RGB) image, and you use a convolutional layer with 100 filters that are each 5x5. How many parameters does this hidden layer have (including the bias parameters)?
- [x] 7600
- [ ] 7500
- [ ] 2501
- [ ] 2600 
> you have 25×3=75 weights and 1 bias per filter. Given that you have 100 filters, you get 7,600 parameters for this layer.
---

### 4. You have an input volume that is 63x63x16, and convolve it with 32 filters that are each 7x7, using a stride of 2 and no padding. What is the output volume?
- [x] 29x29x32
- [ ] 16x16x16
- [ ] 29x29x16
- [ ] 16x16x32
> <img src="https://latex.codecogs.com/svg.image?\frac{63-7-0\times&space;2}{2}&space;&plus;&space;1&space;=&space;29" title="\frac{63-7-0\times 2}{2} + 1 = 29" /> and the number of channels should match the number of filters.
---

### 5. You have an input volume that is 15x15x8, and pad it using “pad=2.” What is the dimension of the resulting volume (after padding)?
- [x] 19x19x8
- [ ] 19x19x12
- [ ] 17x17x8
- [ ] 17x17x10
> padding is applied over the height and the width of the input image. If the padding is two, you add 4 to the height dimension and 4 the width dimension.
---

### 6. You have an input volume that is 63x63x16, and convolve it with 32 filters that are each 7x7, and stride of 1. You want to use a “same” convolution. What is the padding?
- [x] 3
- [ ] 1
- [ ] 7
- [ ] 2
> you need to satisfy the following equation: <img src="https://latex.codecogs.com/svg.image?n_H&space;-&space;f&space;&plus;&space;2&space;\times&space;p&space;=&space;n_H" title="n_H - f + 2 \times p = n_H" />   as you want to keep the dimensions between the input volume and the output volume.

---
### 7. You have an input volume that is 32x32x16, and apply max pooling with a stride of 2 and a filter size of 2. What is the output volume?
- [x] 16x16x16
- [ ] 16x16x8
- [ ] 15x15x16
- [ ] 32x32x8
> using the following formula: <img src="https://latex.codecogs.com/svg.image?n_H^{[l]}&space;=&space;\frac{n_H^{[l-1]}&plus;f-2p}{s}" title="n_H^{[l]} = \frac{n_H^{[l-1]}+f-2p}{s}" />
---

### 8. Because pooling layers do not have parameters, they do not affect the backpropagation (derivatives) calculation.
- False
> Everything that influences the loss should appear in the backpropagation because we are computing derivatives. In fact, pooling layers modify the input by choosing one value out of several values in their input volume. Also, to compute derivatives for the layers that have parameters (Convolutions, Fully-Connected), we still need to backpropagate the gradient through the Pooling layers.
---

### 9. In lecture we talked about “parameter sharing” as a benefit of using convolutional networks. Which of the following statements about parameter sharing in ConvNets are true? (Check all that apply.)
- [x] It reduces the total number of parameters, thus reducing overfitting.
- [x] It allows a feature detector to be used in multiple locations throughout the whole input image/input volume.
- [ ] It allows gradient descent to set many of the parameters to zero, thus making the connections sparse.
- [ ] It allows parameters learned for one task to be shared even for a different task (transfer learning).
> by sliding a filter of parameters over the entire input volume, we make sure a feature detector can be used in multiple locations.
> 
> a convolutional layer uses parameter sharing and has usually a lot less parameters than a fully-connected layer.

---
### 10. In lecture we talked about “sparsity of connections” as a benefit of using convolutional layers. What does this mean?
- [x] Each activation in the next layer depends on only a small number of activations from the previous layer.
- [ ] Regularization causes gradient descent to set many of the parameters to zero.
- [ ] Each filter is connected to every channel in the previous layer.
- [ ] Each layer in a convolutional network is connected only to two other layers
> each activation of the output volume is computed by multiplying the parameters from only one filter with a volumic slice of the input volume and then summing all these together. 
