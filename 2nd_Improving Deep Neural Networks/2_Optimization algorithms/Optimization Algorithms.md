# Optimization Algorithms

### 1. Which notation would you use to denote the 3rd layer’s activations when the input is the 7th example from the 8th minibatch?
- <img src="https://latex.codecogs.com/svg.image?a^{[3]{8}(7)}" title="a^{[3]{8}(7)}" />
---

### 2. Which of these statements about mini-batch gradient descent do you agree with?
- [x] One iteration of mini-batch gradient descent (computing on a single mini-batch) is faster than one iteration of batch gradient descent.
- [ ] Training one epoch (one pass through the training set) using mini-batch gradient descent is faster than training one epoch using batch gradient descent.
- [ ] You should implement mini-batch gradient descent without an explicit for-loop over different mini-batches, so that the algorithm processes all mini-batches at the same time (vectorization).
---

### 3. Why is the best mini-batch size usually not 1 and not m, but instead something in-between?
- [ ] If the mini-batch size is m, you end up with stochastic gradient descent, which is usually slower than mini-batch gradient descent.
- [ ] If the mini-batch size is 1, you end up having to process the entire training set before making any progress.
- [x] If the mini-batch size is 1, you lose the benefits of vectorization across examples in the mini-batch.
- [x] If the mini-batch size is m, you end up with batch gradient descent, which has to process the whole training set before making progress.
---

### 4. Suppose your learning algorithm’s cost **_J_**, plotted as a function of the number of iterations, looks like this: 
<p align="center">
  <img width="50%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/2nd_Improving%20Deep%20Neural%20Networks/2_Optimization%20algorithms/C2W2_Q_image/4.png">
</p>

Which of the following do you agree with?
- [ ] If you’re using mini-batch gradient descent, something is wrong. But if you’re using batch gradient descent, this looks acceptable.
- [x] If you’re using mini-batch gradient descent, this looks acceptable. But if you’re using batch gradient descent, something is wrong.
- [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, something is wrong.
- [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, this looks acceptable.
---

### 5. Suppose the temperature in Casablanca over the first two days of January are the same:
- Jan 1st: <img src="https://latex.codecogs.com/svg.image?\theta_{1}&space;=&space;10^{\circ}C" title="\theta_{1} = 10^{\circ}C" />
- Jan 2nd: <img src="https://latex.codecogs.com/svg.image?\theta_{2}&space;=&space;10^{\circ}C" title="\theta_{2} = 10^{\circ}C" />   
(We used Fahrenheit in lecture, so will use Celsius here in honor of the metric world.) 
Say you use an exponentially weighted average with <img src="https://latex.codecogs.com/svg.image?\beta&space;=&space;0.5&space;" title="\beta = 0.5 " /> to track the temperature: <img src="https://latex.codecogs.com/svg.image?v_0&space;=&space;0,&space;v_t&space;=&space;\beta&space;v_{t-1}&space;&plus;&space;(1-\beta)\theta&space;_t" title="v_0 = 0, v_t = \beta v_{t-1} + (1-\beta)\theta _t" />. If <img src="https://latex.codecogs.com/svg.image?v_2" title="v_2" /> is the value computed after day 2 without bias correction, and <img src="https://latex.codecogs.com/svg.image?v_2^{corrected}" title="v_2^{corrected}" /> is the value you compute with bias correction. What are these values? (You might be able to do this without a calculator, but you don't actually need one. Remember what bias correction is doing.)
- <img src="https://latex.codecogs.com/svg.image?v_2&space;=&space;7.5,&space;v_2^{corrected}&space;=&space;10" title="v_2 = 7.5, v_2^{corrected} = 10" />

---
### 6. Which of these is NOT a good learning rate decay scheme? Here, t is the epoch number. 
- <img src="https://latex.codecogs.com/svg.image?\alpha&space;=&space;e^t&space;\alpha&space;_0" title="\alpha = e^t \alpha _0" />
---
### 7. You use an exponentially weighted average on the London temperature dataset. You use the following to track the temperature: <img src="https://latex.codecogs.com/svg.image?v_t&space;=&space;&space;\beta&space;v_{t-1}&space;&plus;&space;(1-\beta)&space;\theta&space;_t" title="v_t = \beta v_{t-1} + (1-\beta) \theta _t" />. The red line below was computed using <img src="https://latex.codecogs.com/svg.image?\beta&space;=&space;0.9" title="\beta = 0.9" /> . What would happen to your red curve as you vary <img src="https://latex.codecogs.com/svg.image?\beta" title="\beta" />? (Check the two that apply)
<p align="center">
  <img width="60%" height="60%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/2nd_Improving%20Deep%20Neural%20Networks/2_Optimization%20algorithms/C2W2_Q_image/7.png">
</p>

- Incresing <img src="https://latex.codecogs.com/svg.image?\beta" title="\beta" /> will shift the red line slightly to the right.
- Decresing <img src="https://latex.codecogs.com/svg.image?\beta" title="\beta" /> will create more oscillation within the red line.

> Remember that the red line corresponds to β=0.9. In lecture we had a green line β=0.98 that is slightly shifted to the right.
>
> Remember that the red line corresponds to β=0.9. In lecture we had a yellow line β=0.98 that had a lot of oscillations.
---

### 8. Consider this figure:
<p align="center">
  <img width="50%" height="60%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/2nd_Improving%20Deep%20Neural%20Networks/2_Optimization%20algorithms/C2W2_Q_image/8.png">
</p>

These plots were generated with gradient descent; with gradient descent with momentum (β=0.5) and gradient descent with momentum (β=0.9). Which curve corresponds to which algorithm?

- (1) is gradient descent. (2) is gradient descent with momentum (small β). (3) is gradient descent with momentum (large β)
---
### 9. Suppose batch gradient descent in a deep network is taking excessively long to find a value of the parameters that achieves a small value for the cost function <img src="https://latex.codecogs.com/svg.image?\mathcal{J}(W^{[l]},&space;b^{[l]},&space;...,&space;W^{[L]},&space;b^{[L]})" title="\mathcal{J}(W^{[l]}, b^{[l]}, ..., W^{[L]}, b^{[L]})" />. Which of the following techniques could help find parameter values that attain a small value for <img src="https://latex.codecogs.com/svg.image?\mathcal{J}" title="\mathcal{J}" />? (Check all that apply)
- [x] Try tuning the learning rate <img src="https://latex.codecogs.com/svg.image?\alpha&space;" title="\alpha " />
- [x] Try mini-batch gradient descent
- [x] Try using Adam
- [x] Try better random initialization for the weights
- [ ] Try initializing all the weights to zero
---
### 10. Which of the following statements about Adam is False?
- [ ] Adam combines the advantages of RMSProp and momentum
- [ ] The learning rate hyperparameter \alphaα in Adam usually needs to be tuned.
- [ ] We usually use “default” values for the hyperparameters <img src="https://latex.codecogs.com/svg.image?\beta_1,&space;\beta_2&space;" title="\beta_1, \beta_2 " /> and <img src="https://latex.codecogs.com/svg.image?\epsilon" title="\epsilon" /> in Adam (<img src="https://latex.codecogs.com/svg.image?beta_1&space;=&space;0.9,&space;\beta_2&space;=&space;0.999,&space;\epsilon&space;=&space;10^{-8}" title="beta_1 = 0.9, \beta_2 = 0.999, \epsilon = 10^{-8}" />) 
- [x] Adam should be used with batch gradient computations, not with mini-batches.