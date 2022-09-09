## Week 1 Quiz - Recurrent Neural Networks


#### 1. Suppose your training examples are sentences (sequences of words). Which of the following refers to the $l^{th}$ word in the $k^{th}$ training example?
- [x] **$x^{(k)< l>}$**
- [ ] ...

> 📌 The parentheses represent the training example and the brackets represent the word. You should choose the training example and then the word.


#### 2. Consider this RNN:

![image](https://user-images.githubusercontent.com/55765292/189322653-cc467773-8e26-4efd-ba80-0a47c1b71581.png)

**True/False: This specific type of architecture is appropriate when $T_x>T_y$**
- [ ] True
- [x] **False**

> 📌 This type of architecture is for applications where the input and output sequence length is the same.


#### 3. Select the two tasks combination that could be addressed by a many-to-one RNN model architecture from the following:

- [ ] **Task 1:** Speech recognition. **Task 2:** Gender recognition
- [ ] **Task 1:** Image classification. **Task 2:** Sentiment classification.
- [x] **Task 1:** Gender recognition from audio. **Task 2:** Movie review (positive/negative) classification.
- [ ] **Task 1:** Gender recognition from audio. **Task 2:** Image classification.

> 📌 Gender recognition from audio and movie review classification are two examples of many-to-one RNN architecture


#### 4. Using this as the training model below, answer the following:

![image](https://user-images.githubusercontent.com/55765292/189323443-f82f2210-2f4b-4142-b7f2-b078cd824aa1.png)

**True/False: At the $t^{th}$t time step the RNN is estimating $P(y^{< t>} \mid y^{<1>}, y^{<2>}, …, y^{< t-1>})$**

- [x] **True**
- [ ] False

> 📌 In a training model we try to predict the next step based on knowledge of all prior steps.


#### 5. You have finished training a language model RNN and are using it to sample random sentences, as follows:

![image](https://user-images.githubusercontent.com/55765292/189323818-441f41df-f6ae-4cab-ba39-ef3806f78373.png)

**True/False: In this sample sentence, step t uses the probabilities output by the RNN to randomly sample a chosen word for that time-step. Then it passes this selected word to the next time-step.**

- [x] **True**
- [ ] False

> 📌 Step t uses the probabilities output by the RNN to randomly sample a chosen word for that time-step. Then it passes this selected word to the next time-step.


#### 6. True/False: If you are training an RNN model, and find that your weights and activations are all taking on the value of NaN (“Not a Number”) then you have an exploding gradient problem.

- [x] **True**
- [ ] False

> 📌 Exploding gradients happen when large error gradients accumulate and result in very large updates to the NN model weights during training. These weights can become too large and cause an overflow, identified as NaN.


#### 7. Suppose you are training an LSTM. You have an 80000 word vocabulary, and are using an LSTM with 800-dimensional activations $a^{< t>}$. What is the dimension of $\Gamma_u$ at each time step?

- [x] **800**
- [ ] ...

> 📌 $\Gamma_u$ is a vector of dimension equal to the number of hidden units in the LSTM.


#### 8. True/False: In order to simplify the GRU without vanishing gradient problems even when training on very long sequences you should remove the $\Gamma_r$ i.e., setting $\Gamma_r = 1$ always.

- [x] **True**
- [ ] False

> 📌 If $\Gamma_u \approx 0$ for a timestep, the gradient can propagate back through that timestep without much decay. For the signal to backpropagate without vanishing, we need $c^{< t>}$ to be highly dependent on $c^{< t-1>}$.


#### 9. True/False: Using the equations for the GRU and LSTM below the Update Gate and Forget Gate in the LSTM play a role similar to $1 - \Gamma_u$ and $\Gamma_u$.

![image](https://user-images.githubusercontent.com/55765292/189325024-c2d73fc4-498a-44d5-9794-09b8016299ca.png)

- [ ] True
- [x] **False**

> 📌 No. Instead of using $\Gamma_u$ to compute $1 - \Gamma_u$, LSTM uses 2 gates ($\Gamma_u$ and $\Gamma_f$) to compute the final value of the hidden state. So, $\Gamma_f$ is used instead of $1 - \Gamma_u$.


#### 10. Your mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as $x^{<1>}, \dots, x^{<365>}$. You’ve also collected data on your mood, which you represent as $y^{<1>}, \dots, y^{<365>}$. You’d like to build a model to map from x → y. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

- [x] Unidirectional RNN, because the value of $y^{< t>}$ depends only on $x^{<1>}, \dots, x^{< t>}$, but not on $x^{<1>}, \dots, x^{<365>}$.
