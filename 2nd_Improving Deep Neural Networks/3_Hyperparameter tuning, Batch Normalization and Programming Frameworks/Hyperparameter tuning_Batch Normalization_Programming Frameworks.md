# Hyperparameter tuning, Batch Normalization, Programming Frameworks

### 1. If searching among a large number of hyperparameters, you should try values in a grid rather than random values, so that you can carry out the search more systematically and not rely on chance. True or False?
- False
---

### 2. Every hyperparameter, if set poorly, can have a huge negative impact on training, and so all hyperparameters are about equally important to tune well. True or False?
- False
> We've seen in lecture that some hyperparameters, such as the learning rate, are more critical than others.
---

### 3. During hyperparameter search, whether you try to babysit one model (“Panda” strategy) or train a lot of models in parallel (“Caviar”) is largely determined by:
- The amount of computational power you can access
---

### 4. If you think <img src="https://latex.codecogs.com/svg.image?\beta&space;" title="\beta " />(hyperparameter for momentum) is between 0.9 and 0.99, which of the following is the recommended way to sample a value for beta?
- r = np.random.rand()
- <img src="https://latex.codecogs.com/svg.image?\beta&space;=&space;1-&space;100^{-r-1}&space;" title="\beta = 1- 100^{-r-1} " />
---

### 5. Finding good hyperparameter values is very time-consuming. So typically you should do it once at the start of the project, and try to find very good hyperparameters so that you don’t ever have to revisit tuning them again. True or false?
- False
---

### 6. In batch normalization as presented in the videos, if you apply it on the llth layer of your neural network, what are you normalizing?
- <img src="https://latex.codecogs.com/svg.image?z^{[l]}" title="z^{[l]}" />
---
### 7. In the normalization formula <img src="https://latex.codecogs.com/svg.image?z_{norm}^{(i)}&space;=&space;\frac{z^(i)&space;-&space;\mu&space;}{\sqrt{\sigma&space;^2&space;&plus;&space;\varepsilon&space;}}" title="z_{norm}^{(i)} = \frac{z^(i) - \mu }{\sqrt{\sigma ^2 + \varepsilon }}" />, why do we use epsilon?
- To avoid division by zero
---

### 8. Which of the following statements about \gammaγ and \betaβ in Batch Norm are true? 

---
### 9.

---
### 10.
