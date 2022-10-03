## Week 3 Quiz - Sequence Models & Attention Mechanism

</br>

#### 1. Consider using this encoder-decoder model for machine translation.

![image](https://user-images.githubusercontent.com/55765292/193560604-8bf17e4a-e68a-431e-914a-ee0f8f7cbafc.png)

**This model is a “conditional language model” in the sense that the encoder portion (shown in green) is modeling the probability of the input sentence xx.**
- [ ] True
- [x] **False**

</br>

#### 2. In beam search, if you increase the beam width B, which of the following would you expect to be true?
- [ ] Beam search will use up less memory.
- [x] **Beam search will generally find better solutions (i.e. do a better job maximizing $P(y \mid x)$).**
- [ ] Beam search will run more quickly.
- [ ] Beam search will converge after fewer steps.

> 📌 As the beam width increases, beam search runs more slowly, uses up more memory, and converges after more steps, but generally finds better solutions.

</br>

#### 3. In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly short translations.
- [x] **True**
- [ ] False

</br>

#### 4. Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip xx to a text transcript yy. Your algorithm uses beam search to try to find the value of y that maximizes P(y \mid x).

**On a dev set example, given an input audio clip, your algorithm outputs the transcript $\hat{y}$ = = “I’m building an A Eye system in Silly con Valley.”, whereas a human gives a much superior transcript $y^{ * }$ = “I’m building an AI system in Silicon Valley.”**

**According to your model,**

$P(\hat{y} \mid x) = 7.21 * 10^{-8}$

<br/>

$P(y^{ * } \mid x) = 1.09 * 10^{-7}$

**Would you expect increasing the beam width BB to help correct this example?**
- [ ] No, because $P(y^{ * } | x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the search algorithm rather than the RNN.
- [x] **No, because $P(y^{ * } | x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the RNN rather than to the search algorithm.**
- [ ] Yes, because $P(y^{ * } | x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the search algorithm rather than the RNN.
- [ ] Yes, because $P(y^{ * } | x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the RNN rather than to the search algorithm.

> 📌 $P(y^{ * } \mid x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the search algorithm rather than to the RNN. Increasing the beam width will generally allow beam search to find better solutions.

</br>

#### 5. Continuing the example from Q4, suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake,  $P(y^{ * } \mid x) > P(\hat{y} \mid x)$. This suggests you should not focus your attention on improving the search algorithm.
- [ ] True
- [x] **False**

> 📌 $P(y^{ * } \mid x) > P(\hat{y} \mid x)$ indicates the error should be attributed to the search algorithm rather than to the RNN.

</br>

#### 6. Consider the attention model for machine translation.

![image](https://user-images.githubusercontent.com/55765292/193564001-d990cad6-bd7c-4993-837b-c45b9b0a9ed8.png)

**Further, here is the formula for $\alpha^{< t,t’>}$.**

![image](https://user-images.githubusercontent.com/55765292/193564075-03d4c464-1792-4d29-aecb-a43efc80c475.png)

**Which of the following statements about $\alpha^{< t,t’>}$ are true? Check all that apply.**

- [ ] $\alpha^{< t,t’>}$ is equal to the amount of attention $y^{< t>}$ should pay to $\alpha^{< t'>}$
- [x] **We expect $\alpha^{< t,t’>}$ to be generally larger for values of $\alpha^{< t’>}$ that are highly relevant to the value the network should output for $y^{< t'>}$. (Note the indices in the superscripts.)**
- [ ] $\sum\limits_{t'} \alpha^{< t,t'>} = 0$. (Note the summation is over t'.)
- [x] **$\sum\limits_{t'} \alpha^{< t,t'>} = 1$. (Note the summation is over t'.)**

</br>

#### 7. The network learns where to “pay attention” by learning the values $e^{< t,t’>}, which are computed using a small neural network:

**We can't replace $s^{< t-1>}$ with s^{< t>} as an input to this neural network. This is because $s^{< t>}$ depends on $\alpha^{< t,t’>}$ which in turn depends on $e^{< t,t’>}$ so at the time we need to evaluate this network, we haven’t computed $s^{< t>}$ yet.**
- [x] **True**
- [ ] False

</br>

#### 8. Compared to the encoder-decoder model shown in Question 1 of this quiz (which does not use an attention mechanism), we expect the attention model to have the greatest advantage when:
- [ ] The input sequence length $T_x$ is small.
- [x] **The input sequence length $T_x$ is large.**

</br>

#### 9. Under the CTC model, identical repeated characters not separated by the “blank” character ( _ ) are collapsed. Under the CTC model, what does the following string collapse to?

**__c_oo_o_kk___b_ooooo__oo__kkk**
- [ ] cook book
- [ ] coookkboooooookkk
- [ ] cokbok
- [x] **cookbook** 

</br>

#### 10. In trigger word detection, $x^{< t>}$ is:
- [ ] The $t^{-th}$ input word, represented as either a one-hot vector or a word embedding.
- [x] **Features of the audio (such as spectrogram features) at time $t$.**
- [ ] Whether the trigger word is being said at time $t$.
- [ ] Whether someone has just finished saying the trigger word at time $t$.
