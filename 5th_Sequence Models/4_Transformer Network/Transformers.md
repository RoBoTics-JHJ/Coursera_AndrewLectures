# Transformers

### 1. A Transformer Network, like its predecessors RNNs, GRUs and LSTMs, can process information one word at a time. (Sequential architecture).
- False
> A Transformer Network can ingest entire sentences all at the same time.
---

### 2. Transformer Network methodology is taken from: (Check all that apply)
- [x] Convolutional Neural Network style of processing.
- [x] Attention mechanism.
- [ ] None of these.
- [ ] Convolutional Neural Network style of architecture.
---

### 3. The concept of Self-Attention is that:
<p align="center">
  <img width="60%" height="50%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/4_Transformer%20Network/C5W4_Q_image/3.png">
</p>

- Given a word, its neighbouring words are used to compute its context by summing up the word values to map the Attention related to that given word.

---

### 4. Which of the following correctly represents Attention ?
- <img src="https://latex.codecogs.com/svg.image?Attention(Q,K,V)&space;=&space;softmax(\frac{QV^T}{\sqrt{d_k}})V" title="Attention(Q,K,V) = softmax(\frac{QV^T}{\sqrt{d_k}})V" />
---

### 5. Are the following statements true regarding Query (Q), Key (K) and Value (V) ?
Q = interesting questions about the words in a sentence

K = specific representations of words given a Q

V = qualities of words given a Q
- False
---

### 6.

<img src="https://latex.codecogs.com/svg.image?Attention(W_i^QQ,&space;W_i^KK,&space;W_i^VV)" title="Attention(W_i^QQ, W_i^KK, W_i^VV)" />
<img src="https://latex.codecogs.com/svg.image?i" title="i" /> here represents the computed attention weight matrix associated with the <img src="https://latex.codecogs.com/svg.image?ith" title="ith" /> "word" in a sentence.
- False
> i here represents the computed attention weight matrix associated with the ith “head” (sequence).
---

### 7. Following is the architecture within a Transformer Network. **(without displaying positional encoding and output layers(s))**
<p align="center">
  <img width="55%" height="65%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/4_Transformer%20Network/C5W4_Q_image/7.png">
</p>

What information does the Decoder take from the Encoder for its second block of Multi-Head Attention ? (Marked XX, pointed by the independent arrow)
- V
- K
---

### 8. Following is the architecture within a Transformer Network. (without displaying positional encoding and output layers(s))
<p align="center">
  <img width="55%" height="65%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/5th_Sequence%20Models/4_Transformer%20Network/C5W4_Q_image/8.png">
</p>

What is the output layer(s) of the Decoder ? (Marked YY, pointed by the independent arrow)
- [x] Linear layer followed by a softmax layer.
- [ ] Softmax layer
- [ ] Softmax layer followed by a linear layer.
- [ ] Linear layer
---

### 9. Why is positional encoding important in the translation process? (Check all that apply)
- [x] Position and word order are essential in sentence construction of any language.
- [x] Providing extra information to our model.
- [ ] It helps to locate every word within a sentence.
- [ ] It is used in CNN and works well there.
___

### 10. Which of these is a good criteria for a good positionial encoding algorithm?
- [x] It should output a unique encoding for each time-step (word’s position in a sentence).
- [x] Distance between any two time-steps should be consistent for all sentence lengths.
- [x] The algorithm should be able to generalize to longer sentences.
- [ ] None of the these.

