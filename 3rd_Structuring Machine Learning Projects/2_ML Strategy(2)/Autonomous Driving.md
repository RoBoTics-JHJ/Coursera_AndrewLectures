# Autonomous Driving (Case Study)

### 1.
To help you practice strategies for machine learning, in this week we’ll present another scenario and ask how you would act. We think this “simulator” of working in a machine learning project will give a task of what leading a machine learning project could be like!

You are employed by a startup building self-driving cars. You are in charge of detecting road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. As an example, the above image contains a pedestrian crossing sign and red traffic lights

<p align="center">
  <img width="60%" height="60%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/3rd_Structuring%20Machine%20Learning%20Projects/2_ML%20Strategy(2)/C3W2_Q_image/1.png">
</p>

Your 100,000 labeled images are taken using the front-facing camera of your car. This is also the distribution of data you care most about doing well on. You think you might be able to get a much larger dataset off the internet, that could be helpful for training even if the distribution of internet data is not the same. 

You are just getting started on this project. What is the first thing you do? Assume each of the steps below would take about an equal amount of time (a few days).

- [x] Spend a few days training a basic model and see what mistakes it makes.
- [ ] Spend a few days collecting more data using the front-facing camera of your car, to better understand how much data per unit time you can collect.
- [ ] Spend a few days checking what is human-level performance for these tasks so that you can get an accurate estimate of Bayes error.
- [ ] Spend a few days getting the internet data, so that you understand better what data is available. 

> As discussed in lecture, applied ML is a highly iterative process. If you train a basic model and carry out error analysis (see what mistakes it makes) it will help point you in more promising directions. 

---
### 2.
Your goal is to detect road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. You plan to use a deep neural network with ReLU units in the hidden layers.

For the output layer, a softmax activation would be a good choice for the output layer because this is a multi-task learning problem. True/False?

- False

> Softmax would be a good choice if one and only one of the possibilities (stop sign, speed bump, pedestrian crossing, green light and red light) was present in each image.
---

### 3. You are carrying out error analysis and counting up what errors the algorithm makes. Which of these datasets do you think you should manually go through and carefully examine, one image at a time?
- [x] 500 images on which the algorithm made a mistake
- [ ] 10,000 randomly chosen images
- [ ] 10,000 images on which the algorithm made a mistake
- [ ] 500 randomly chosen images
> Focus on images that the algorithm got wrong. Also, 500 is enough to give you a good initial sense of the error statistics. There’s probably no need to look at 10,000, which will take a long time. 

---

### 4. After working on the data for several weeks, your team ends up with the following data:
- 100,000 labeled images taken using the front-facing camera of your car.
- 900,000 labeled images of roads downloaded from the internet.
- Each image’s labels precisely indicate the presence of any specific road signs and traffic signals or combinations of them. For example <img src="https://latex.codecogs.com/svg.image?y^{(i)}&space;=&space;\begin{bmatrix}1&space;\\0&space;\\0&space;\\1&space;\\0\end{bmatrix}" title="y^{(i)} = \begin{bmatrix}1 \\0 \\0 \\1 \\0\end{bmatrix}" /> means the image contains a stop sign and a red traffic light. Because this is a multi-task learning problem, you need to have all your <img src="https://latex.codecogs.com/svg.image?y^{(i)}" title="y^{(i)}" /> vectors fully labeled. If one example is equal to <img src="https://latex.codecogs.com/svg.image?\begin{bmatrix}0&space;\\?&space;\\1&space;\\1&space;\\?\end{bmatrix}" title="\begin{bmatrix}0 \\? \\1 \\1 \\?\end{bmatrix}" /> then the learning algorithm will not be able to use that example. True/False?

-Fasle

---
### 5.

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
<p align="center">
  <img width="70%" height="70%" src="">
</p>

---
### 11.

---
### 12.

---
### 13.

---
### 14.

---
### 15.