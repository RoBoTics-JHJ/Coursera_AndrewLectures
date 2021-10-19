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

### 5. Let _E_ be an embedding matrix, and let <img src="https://latex.codecogs.com/svg.image?o_{1234}" title="o_{1234}" /> be a one-hot vector corresponding to word 1234. Then to get the embedding of word 1234, why don’t we call <img src="https://latex.codecogs.com/svg.image?E&space;*&space;o_{1234}" title="E * o_{1234}" /> in Python?
- [x] It is computationally wasteful.
- [ ] This doesn’t handle unknown words (\<UNK>).
- [ ] None of the above: calling the Python snippet as described above is fine.
- [ ] The correct formula is <img src="https://latex.codecogs.com/svg.image?E^T&space;*&space;o_{1234}" title="E^T * o_{1234}" />.
> The element-wise multiplication will be extremely inefficient.

### 6. When learning word embeddings, we create an artificial task of estimating <img src="https://latex.codecogs.com/svg.image?P(target|context)" title="P(target|context)" />. It is okay if we do poorly on this artificial prediction task; the more important by-product of this task is that we learn a useful set of word embeddings.
- True

### 7. In the word2vec algorithm, you estimate <img src="https://latex.codecogs.com/svg.image?P(t|c)" title="P(t|c)" />, where tt is the target word and cc is a context word. How are tt and cc chosen from the training set? Pick the best answer.
- [x] c and t are chosen to be nearby words.
- [ ] c is the one word that comes immediately before t.
- [ ] c is a sequence of several words immediately before t.
- [ ] c is the sequence of all the words in the sentence before t.

### 8. Suppose you have a 10000 word vocabulary, and are learning 500-dimensional word embeddings. The word2vec model uses the following softmax function:
<img src="https://latex.codecogs.com/svg.image?P(t|c)&space;=&space;\frac{e^{\theta^\frac{T}{t}e_c}}{\sum_{t^{'}=1}^{10000}e^{\theta&space;\frac{T}{t^{'}}e_c}}" title="P(t|c) = \frac{e^{\theta^\frac{T}{t}e_c}}{\sum_{t^{'}=1}^{10000}e^{\theta \frac{T}{t^{'}}e_c}}" />
Which of these statements are correct? Check all that apply.
- <img src="https://latex.codecogs.com/svg.image?\theta_t&space;" title="\theta_t " /> and <img src="https://latex.codecogs.com/svg.image?e_c" title="e_c" /> are both 500 dimensional vectors.
- <img src="https://latex.codecogs.com/svg.image?\theta_t&space;" title="\theta_t " /> and <img src="https://latex.codecogs.com/svg.image?e_c" title="e_c" /> are both trained with an optimization algorithm such as Adam or gradient descent.

### 9. Suppose you have a 10000 word vocabulary, and are learning 500-dimensional word embeddings.The GloVe model minimizes this objective:
<img src="https://latex.codecogs.com/svg.image?min\sum_{i=1}^{10,000}\sum_{j=1}^{10,000}f(X_{ij})(\theta_i^Te_j&space;&plus;&space;b_i&space;&plus;&space;b_j^{'}&space;-&space;\log&space;X_{ij})^2" title="min\sum_{i=1}^{10,000}\sum_{j=1}^{10,000}f(X_{ij})(\theta_i^Te_j + b_i + b_j^{'} - \log X_{ij})^2" />
Which of these statements are correct? Check all that apply.

- <img src="https://latex.codecogs.com/svg.image?\theta_i" title="\theta_i" /> and <img src="https://latex.codecogs.com/svg.image?e_j" title="e_j" /> should be initialized randomly at the beginning of training.
- <img src="https://latex.codecogs.com/svg.image?X_{ij}" title="X_{ij}" /> is the number of times word j appears in the context of word i.
- The weighting <img src="https://latex.codecogs.com/svg.image?f(.)" title="f(.)" /> function  must satisfy <img src="https://latex.codecogs.com/svg.image?f(0)&space;=&space;0" title="f(0) = 0" />.
> The weighting function helps prevent learning only from extremely common word pairs. It is not necessary that it satisfies this function.

### 10. You have trained word embeddings using a text dataset of <img src="https://latex.codecogs.com/svg.image?m_1" title="m_1" /> words. You are considering using these word embeddings for a language task, for which you have a separate labeled dataset of <img src="https://latex.codecogs.com/svg.image?m_2" title="m_2" />  words. Keeping in mind that using word embeddings is a form of transfer learning, under which of these circumstances would you expect the word embeddings to be helpful?
- <img src="https://latex.codecogs.com/svg.image?m_1" title="m_1" /> >> <img src="https://latex.codecogs.com/svg.image?m_2" title="m_2" />






