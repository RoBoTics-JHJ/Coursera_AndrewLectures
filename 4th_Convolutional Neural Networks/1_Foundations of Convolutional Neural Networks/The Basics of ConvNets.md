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
> you have 25×3=75 weights and 11 bias per filter. Given that you have 100 filters, you get 7,600 parameters for this layer.
---

### 4. Which of the following is a correct definition of the triplet loss? Consider that α>0. (We encourage you to figure out the answer from first principles, rather than just refer to the lecture.)
- <img src="https://latex.codecogs.com/svg.image?max(\left\|&space;f(A)&space;-&space;f(P)\right\|^2&space;-&space;\left\|&space;f(a)&space;-&space;f(N)\right\|^2&space;&plus;&space;\alpha,&space;0)" title="max(\left\| f(A) - f(P)\right\|^2 - \left\| f(a) - f(N)\right\|^2 + \alpha, 0)" />
---

### 5. Consider the following Siamese network architecture: 
<p align="center">
  <img width="70%" height="70%" src="">
</p>



---

### 6.

---
### 7.

---
### 8.

---
### 9.

---
### 10.
