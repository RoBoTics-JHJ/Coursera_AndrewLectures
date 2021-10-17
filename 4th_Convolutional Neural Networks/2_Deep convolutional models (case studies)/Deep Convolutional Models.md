# Deep Convolutional Models

### 1. Which of the following do you typically see in a ConvNet? (Check all that apply.)
- [x] FC layers in the last few layers
- [x] Multiple CONV layers followed by a POOL layer
- [ ] Multiple POOL layers followed by a CONV layer
- [ ] FC layers in the first few layers
> fully-connected layers are often used after flattening a volume to output a set of classes in classification.
> 
> as seen in the case studies.
---

### 2. In order to be able to build very deep networks, we usually only use pooling layers to downsize the height/width of the activation volumes while convolutions are used with “valid” padding. Otherwise, we would downsize the input of the model too quickly.
- False
---

### 3. Training a deeper network (for example, adding additional layers to the network) allows the network to fit more complex functions and thus almost always results in lower training error. For this question, assume we’re referring to “plain” networks. 
- False
---

### 4. The following equation captures the computation in a ResNet block. What goes into the two (...) above? 
<img src="https://latex.codecogs.com/svg.image?a^{[l&plus;2]}&space;=&space;g(W^{[l&plus;2]}g(W^{[l&plus;1]}a^{[l]}&space;&plus;&space;b^{[l&plus;1]})&space;&plus;&space;b^{l&plus;2}&space;&plus;&space;...&space;)&space;&plus;&space;..." title="a^{[l+2]} = g(W^{[l+2]}g(W^{[l+1]}a^{[l]} + b^{[l+1]}) + b^{l+2} + ... ) + ..." />

-  <img src="https://latex.codecogs.com/svg.image?a^{[l]}" title="a^{[l]}" /> and 0, respectively
---

### 5. Which ones of the following statements on Residual Networks are true? (Check all that apply.)
- [x] The skip-connection makes it easy for the network to learn an identity mapping between the input and the output within the ResNet block.
- [x] Using a skip-connection helps the gradient to backpropagate and thus helps you to train deeper networks
- [ ] A ResNet with L layers would have on the order of <img src="https://latex.codecogs.com/svg.image?L^2" title="L^2" /> skip connections in total.
- [ ] The skip-connections compute a complex non-linear function of the input to pass to a deeper layer in the network.
---

### 6. Suppose you have an input volume of dimension <img src="https://latex.codecogs.com/svg.image?n_H&space;\times&space;n_W&space;\times&space;n_C" title="n_H \times n_W \times n_C" />. Which of the following statements you agree with? (Assume that “1x1 convolutional layer” below always uses a stride of 1 and no padding.)
- You can use a 1x1 convolutional layer to reduce <img src="https://latex.codecogs.com/svg.image?n_C" title="n_C" /> but not <img src="https://latex.codecogs.com/svg.image?n_H" title="n_H" />, <img src="https://latex.codecogs.com/svg.image?n_W" title="n_W" />.
- You can use a 2D pooling layer to reduce <img src="https://latex.codecogs.com/svg.image?n_H" title="n_H" />, <img src="https://latex.codecogs.com/svg.image?n_W" title="n_W" />, but not <img src="https://latex.codecogs.com/svg.image?n_C" title="n_C" />.
> a 1x1 convolutional layer with a small number of filters is going to reduce <img src="https://latex.codecogs.com/svg.image?n_C" title="n_C" /> but will keep the dimensions <img src="https://latex.codecogs.com/svg.image?n_H" title="n_H" /> and <img src="https://latex.codecogs.com/svg.image?n_W" title="n_W" />

---

### 7. Which ones of the following statements on Inception Networks are true? (Check all that apply.)
- [x] Inception blocks usually use 1x1 convolutions to reduce the input data volume’s size before applying 3x3 and 5x5 convolutions.
- [x] A single inception block allows the network to use a combination of 1x1, 3x3, 5x5 convolutions and pooling.
- [ ] Making an inception network deeper (by stacking more inception blocks together) might not hurt training set performance.
- [ ] Inception networks incorporate a variety of network architectures (similar to dropout, which randomly chooses a network architecture on each step) and thus has a similar regularizing effect as dropout.
---

### 8. Which of the following are common reasons for using open-source implementations of ConvNets (both the model and/or weights)? Check all that apply.
- [x] Parameters trained for one computer vision task are often useful as pretraining for other computer vision tasks.
- [x] It is a convenient way to get working with an implementation of a complex ConvNet architecture.
- [ ] The same techniques for winning computer vision competitions, such as using multiple crops at test time, are widely used in practical deployments (or production system deployments) of ConvNets.
- [ ] A model trained for one computer vision task can usually be used to perform data augmentation even for a different computer vision task.
---

### 9. In Depthwise Separable Convolution you:
- Perform two steps of convolution.
- You convolve the input image with <img src="https://latex.codecogs.com/svg.image?n_c" title="n_c" /> numbeer of <img src="https://latex.codecogs.com/svg.image?n_f&space;\times&space;n_f&space;" title="n_f \times n_f " /> filters (<img src="https://latex.codecogs.com/svg.image?n_c" title="n_c" /> is the number of color channels of the input image)
---

### 10. Fill in the missing dimensions shown in the image below (marked W, Y, Z).
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/2_Deep%20convolutional%20models%20(case%20studies)/C4W2_Q_image/10.png">
</p>

- W = 5, Y =30, Z = 20