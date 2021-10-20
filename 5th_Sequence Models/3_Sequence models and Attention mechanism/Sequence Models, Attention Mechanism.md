# Sequence Models & Attention Mechanism

### 1. Consider using this encoder-decoder model for machine translation.
<p align="center">
  <img width="40%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/3_Sequence%20models%20and%20Attention%20mechanism/C5W3_Q_image/1.png">
</p>

This model is a “conditional language model” in the sense that the encoder portion (shown in green) is modeling the probability of the input sentence _x_.
- False
---

### 2. In beam search, if you increase the beam width <img src="https://latex.codecogs.com/svg.image?B" title="B" />, which of the following would you expect to be true? Check all that apply.
- [x] Beam search will generally find better solutions (i.e. do a better job maximizing <img src="https://latex.codecogs.com/svg.image?P(y|x)" title="P(y|x)" />)
- [x] Beam search will run more slowly.
- [x] Beam search will use up more memory.
- [ ] Beam search will converge after fewer steps. 
---

### 3. In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly short translations. 
- True
---

### 4. 
Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip <img src="https://latex.codecogs.com/svg.image?x" title="x" /> to a text transcript <img src="https://latex.codecogs.com/svg.image?y" title="y" />. Your algorithm uses beam search to try to find the value of <img src="https://latex.codecogs.com/svg.image?y" title="y" /> that maximizes <img src="https://latex.codecogs.com/svg.image?P(y|x)" title="P(y|x)" />.

On a dev set example, given an input audio clip, your algorithm outputs the transcript <img src="https://latex.codecogs.com/svg.image?\hat{y}" title="\hat{y}" /> = "I'm building an A Eye system in Silicon Valley.", whereas a human gives a much superior transcript <img src="https://latex.codecogs.com/svg.image?y^{*}" title="y^{*}" /> = "I'm building an AI system in Silicon Valley."

According to your model,

<img src="https://latex.codecogs.com/svg.image?P(\hat{y}|x)&space;=&space;1.09&space;*&space;10&space;-&space;7" title="P(\hat{y}|x) = 1.09 * 10 - 7" />        
   
<img src="https://latex.codecogs.com/svg.image?P(y^*|x)&space;=&space;7.21*&space;10&space;-&space;8" title="P(y^*|x) = 7.21* 10 - 8" />

Would you expect increasing the beam width B to help correct this example?
- No, because <img src="https://latex.codecogs.com/svg.image?P(y^*|x)&space;\leq&space;P(\hat{y}|x)" title="P(y^*|x) \leq P(\hat{y}|x)" /> indicates the error should be attributed to the RNN rather than to the search algorithm.
---

### 5. Continuing the example from Q4, suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake, <img src="https://latex.codecogs.com/svg.image?P(y^*|x)&space;>&space;P(\hat{y}|x)" title="P(y^*|x) > P(\hat{y}|x)" />. This suggests you should focus your attention on improving the search algorithm.
- True
---

### 6. Consider the attention model for machine translation.
<p align="center">
  <img width="55%" height="55%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/3_Sequence%20models%20and%20Attention%20mechanism/C5W3_Q_image/6.png">
</p>

Further, here is the formula for <img src="https://latex.codecogs.com/svg.image?\alpha^{<t,t'>}" title="\alpha^{<t,t'>}" />.

<p align="center">
  <img width="30%" height="30%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/3_Sequence%20models%20and%20Attention%20mechanism/C5W3_Q_image/6_1.png">
</p>

Which of the following statements about <img src="https://latex.codecogs.com/svg.image?\alpha^{<t,t'>}" title="\alpha^{<t,t'>}" /> are true? Check all the apply.

- <img src="https://latex.codecogs.com/svg.image?\sum_{t'}^{}&space;\alpha^{<t,t'>}&space;=&space;1" title="\sum_{t'}^{} \alpha^{<t,t'>} = 1" /> (Note the summantion is over <img src="https://latex.codecogs.com/svg.image?t'" title="t'" />.) 
-  We expect <img src="https://latex.codecogs.com/svg.image?\alpha^{<t,t'>}" title="\alpha^{<t,t'>}" /> to be generally larger for values of <img src="https://latex.codecogs.com/svg.image?\alpha^{<t'>}" title="\alpha^{<t'>}" /> that are highly relevant to the value the network should output for <img src="https://latex.codecogs.com/svg.image?y^{<t>}" title="y^{<t>}" />. (Note the indices in the superscripts.)
---

### 7. The network learns where to “pay attention” by learning the values <img src="https://latex.codecogs.com/svg.image?e^{<t,t'>}" title="e^{<t,t'>}" />, which are computed using a small neural network:
We can't replace <img src="https://latex.codecogs.com/svg.image?s^{<t-1>}" title="s^{<t-1>}" /> with <img src="https://latex.codecogs.com/svg.image?s^{<t>}" title="s^{<t>}" /> as an input to this neural network. This is because <img src="https://latex.codecogs.com/svg.image?s^{<t>}" title="s^{<t>}" /> depends on <img src="https://latex.codecogs.com/svg.image?\alpha^{<t,t'>}" title="\alpha^{<t,t'>}" />  which in turn depends on <img src="https://latex.codecogs.com/svg.image?e^{<t,t'>}" title="e^{<t,t'>}" />; so at the time we need to evaluate this network, we haven’t computed <img src="https://latex.codecogs.com/svg.image?s^{<t>}" title="s^{<t>}" /> yet.     
- True
---

### 8. Compared to the encoder-decoder model shown in Question 1 of this quiz (which does not use an attention mechanism), we expect the attention model to have the greatest advantage when:
- The input sequence length <img src="https://latex.codecogs.com/svg.image?T_x" title="T_x" /> is large.
---

### 9. 
Under the CTC model, identical repeated characters not separated by the “blank” character (_) are collapsed. Under the CTC model, what does the following string collapse to?

__c_oo_o_kk___b_ooooo__oo__kkk

- [x] cookbook
- [ ] cook book
- [ ] cokbok
- [ ] coookkboooooookkk
___

### 10. In trigger word detection, <img src="https://latex.codecogs.com/svg.image?x^{<t>}" title="x^{<t>}" /> is:
- [x] Features of the audio (such as spectrogram features) at time t.
- [ ] Whether someone has just finished saying the trigger word at time t.
- [ ] Whether the trigger word is being said at time t.
- [ ] The t-th input word, represented as either a one-hot vector or a word embedding.


