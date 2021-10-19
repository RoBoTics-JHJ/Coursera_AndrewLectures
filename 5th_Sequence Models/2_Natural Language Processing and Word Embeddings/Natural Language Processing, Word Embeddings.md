# Natural Language Processing & Word Embeddings

### 1. Suppose you learn a word embedding for a vocabulary of 10000 words. Then the embedding vectors should be 10000 dimensional, so as to capture the full range of variation and meaning in those words.
- False
> The dimension of word vectors is usually smaller than the size of the vocabulary. Most common sizes for word vectors range between 50 and 400. 
---

### 2. What is t-SNE?
- [x] A non-linear dimensionality reduction technique
- [ ] A supervised learning algorithm for learning word embeddings
- [ ] An open-source sequence modeling library
- [ ] A linear transformation that allows us to solve analogies on word vectors
---

### 3. Suppose you download a pre-trained word embedding which has been trained on a huge corpus of text. You then use this word embedding to train an RNN for a language task of recognizing if someone is happy from a short snippet of text, using a small training set.
x(input text) | y(happy?)
---|---
I'm feeling wonderful today! | 1
I'm bummed my cat is ill. | 0
Really enjoying this! | 1

Then even if the word “ecstatic” does not appear in your small training set, your RNN might reasonably be expected to recognize “I’m ecstatic” as deserving a label _y_ = 1.
- True
> Word vectors empower your model with an incredible ability to generalize. The vector for “ecstatic” would contain a positive/happy connotation which will probably make your model classify the sentence as a "1".
---

### 4. Which of these equations do you think should hold for a good word embedding? (Check all that apply) 
- <img src="https://latex.codecogs.com/svg.image?e_{boy}&space;-&space;e_{girl}&space;\approx&space;e_{brother}&space;-&space;e_{sister}" title="e_{boy} - e_{girl} \approx e_{brother} - e_{sister}" />
- <img src="https://latex.codecogs.com/svg.image?e_{boy}&space;-&space;e_{brother}&space;\approx&space;e_{girl}&space;-&space;e_{sister}" title="e_{boy} - e_{brother} \approx e_{girl} - e_{sister}" />
---

### 5. Let EE be an embedding matrix, and let o_{1234}
1234
​
  be a one-hot vector corresponding to word 1234. Then to get the embedding of word 1234, why don’t we call E * o_{1234}E∗o 
1234
​
  in Python?




