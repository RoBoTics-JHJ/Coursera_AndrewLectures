# Recurrent Neural Networks

### 1. Suppose your training examples are sentences (sequences of words). Which of the following refers to the <img src="https://latex.codecogs.com/svg.image?j^{th}" title="j^{th}" />  word in the <img src="https://latex.codecogs.com/svg.image?i^{th}" title="i^{th}" /> training example?
- <img src="https://latex.codecogs.com/svg.image?x^{(i)<j>}" title="x^{(i)<j>}" />
---

### 2. Consider this RNN:
<p align="center">
  <img width="50%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/2.png">
</p>
This specific type of architecture is appropriate when:

- <img src="https://latex.codecogs.com/svg.image?T_x&space;=&space;T_y" title="T_x = T_y" />
> It is appropriate when every input should be matched to an output.
---

### 3. To which of these tasks would you apply a many-to-one RNN architecture? (Check all that apply).
<p align="center">
  <img width="30%" height="30%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/3.png">
</p>

- [x] Gender recognition from speech (input an audio clip and output a label indicating the speaker’s gender)
- [x] Sentiment classification (input a piece of text and output a 0/1 to denote positive or negative sentiment)
- [ ] Speech recognition (input an audio clip and output a transcript)
- [ ] Image classification (input an image and output a label)
---

### 4. You are training this RNN language model.
<p align="center">
  <img width="30%" height="30%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/4.png">
</p>
At the <img src="https://latex.codecogs.com/svg.image?t^{th}" title="t^{th}" /> time step, what is the RNN doing? Choose the best answer. 

- Estimating <img src="https://latex.codecogs.com/svg.image?P(y^{<t>}|y^{<1>},&space;y^{<2>},&space;...,&space;y^{<t-1>})" title="P(y^{<t>}|y^{<1>}, y^{<2>}, ..., y^{<t-1>})" />
> In a language model we try to predict the next step based on the knowledge of all prior steps.
---

### 5. You have finished training a language model RNN and are using it to sample random sentences, as follows:
<p align="center">
  <img width="60%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/5.png">
</p>

What are you doing at each time step _t_?
- [x] (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as <img src="https://latex.codecogs.com/svg.image?\hat{y}^{<t>}" title="\hat{y}^{<t>}" />.(ii) Then pass this selected word to the next time-step.
- [ ] (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as  <img src="https://latex.codecogs.com/svg.image?\hat{y}^{<t>}" title="\hat{y}^{<t>}" />.(ii) Then pass the ground-truth word from the training set to the next time-step.
- [ ] (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as <img src="https://latex.codecogs.com/svg.image?\hat{y}^{<t>}" title="\hat{y}^{<t>}" />.(ii) Then pass the ground-truth word from the training set to the next time-step.
- [ ] (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as <img src="https://latex.codecogs.com/svg.image?\hat{y}^{<t>}" title="\hat{y}^{<t>}" />.(ii) Then pass this selected word to the next time-step.
---

### 6. You are training an RNN, and find that your weights and activations are all taking on the value of NaN (“Not a Number”). Which of these is the most likely cause of this problem?
- [x] Exploding gradient problem.
- [ ] Vanishing gradient problem.
- [ ] ReLU activation function g(.) used to compute g(z), where z is too large.
- [ ] Sigmoid activation function g(.) used to compute g(z), where z is too large.
---

### 7. Suppose you are training a LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations <img src="https://latex.codecogs.com/svg.image?a^{<t>}" title="a^{<t>}" />. What is the dimension of <img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " /> at each time step?
- 100
> <img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " /> is a vector of dimension equal to the number of hidden units in the LSTM.
---

### 8. Here’re the update equations for the GRU.
<p align="center">
  <img width="50%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/8.png">
</p>

Alice proposes to simplify the GRU by always removing the <img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " />.  I.e., setting <img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " /> = 1. Betty proposes to simplify the GRU by removing the <img src="https://latex.codecogs.com/svg.image?\Gamma_r" title="\Gamma_r" />.  I. e., setting <img src="https://latex.codecogs.com/svg.image?\Gamma_r" title="\Gamma_r" /> = 1 always. Which of these models is more likely to work without vanishing gradient problems even when trained on very long input sequences?    
- Betty’s model (removing <img src="https://latex.codecogs.com/svg.image?\Gamma_r" title="\Gamma_r" />), because if <img src="https://latex.codecogs.com/svg.image?\Gamma_r" title="\Gamma_r" />≈0 for a timestep, the gradient can propagate back through that timestep without much decay. 
>  For the signal to backpropagate without vanishing, we need <img src="https://latex.codecogs.com/svg.image?c^{<t>}" title="c^{<t>}" /> to be highly dependent on <img src="https://latex.codecogs.com/svg.image?c^{<t-1>}" title="c^{<t-1>}" />.
---

### 9. Here are the equations for the GRU and the LSTM:
<p align="center">
  <img width="60%" height="55%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/1_Recurrent%20Neural%20Networks/C5W1_Q_image/9.png">
</p>

From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to _______ and ______ in the GRU. What should go in the blanks?
- <img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " /> and 1-<img src="https://latex.codecogs.com/svg.image?\Gamma_u&space;" title="\Gamma_u " />

---

### 10. You have a pet dog whose mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as <img src="https://latex.codecogs.com/svg.image?x^{<1>},&space;...,&space;x^{<365>}" title="x^{<1>}, ..., x^{<365>}" />. You've also collected data on your dog’s mood, which you represent as <img src="https://latex.codecogs.com/svg.image?y^{<1>},&space;...,&space;y^{<365>}" title="y^{<1>}, ..., y^{<365>}" />. You’d like to build a model to map from <img src="https://latex.codecogs.com/svg.image?x\rightarrow&space;y" title="x\rightarrow y" />. Should you use a Unidirectional RNN or Bidirectional RNN for this problem? 
- Unidirectional RNN, because the value of <img src="https://latex.codecogs.com/svg.image?y^{<t>}" title="y^{<t>}" /> depends only on <img src="https://latex.codecogs.com/svg.image?x^{<1>},&space;...,&space;x^{<t>}" title="x^{<1>}, ..., x^{<t>}" />, but not on <img src="https://latex.codecogs.com/svg.image?x^{<t&plus;1>},&space;...,&space;x^{<365>}" title="x^{<t+1>}, ..., x^{<365>}" />  
