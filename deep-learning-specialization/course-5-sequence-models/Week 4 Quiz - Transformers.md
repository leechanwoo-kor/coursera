## Week 4 Quiz - Transformers

<br>

#### 1. A Transformer Network, like its predecessors RNNs, GRUs and LSTMs, can process information one word at a time. (Sequential architecture).
- [ ] True
- [x] **False**

> 📌 A Transformer Network can ingest entire sentences all at the same time.

#### 1-1. A Transformer Network processes sentences from left to right, one word at a time.
- [ ] True
- [ ] **False**

<br>

#### 2. The major innovation of the transformer architecture is combining the use of LSTMs and RNN sequential processing.
- [ ] True
- [x] **False**

> 📌 The major innovation of the transformer architecture is combining the use of attention based representations and a CNN convolutional neural network style of processing.

#### 2-1. Transformer Network methodology is taken from:
- [ ] RNN and LSTMs
- [ ] Attention Mechanism and RNN style of processing.
- [x] **Attention Mechanism and CNN style of processing.**
- [ ] GRUs and LSTMs

> 📌 Transformer architecture combines the use of attention based representations and a CNN convolutional neural network style of processing.

<br>

#### 3. What are the key inputs to computing the attention value for each word?

![image](https://user-images.githubusercontent.com/55765292/194751349-86a619f5-c35a-42d5-9a65-844879e3c052.png)

- [x] **The key inputs to computing the attention value for each word are called the query, key, and value.**
- [ ] ...

> 📌 The key inputs to computing the attention value for each word are called the query, key, and value.

<br>

#### 4. Which of the following correctly represents Attention ?
- [x] **$Attention(Q,K,V)=softmax(\dfrac{QK^T}{\sqrt{d_k}})V$**
- [ ] $Attention(Q,K,V)=softmax(\dfrac{QV^T}{\sqrt{d_k}})K$
- [ ] $Attention(Q,K,V)=min(\dfrac{QK^T}{\sqrt{d_k}})V$
- [ ] $Attention(Q,K,V)=min(\dfrac{QV^T}{\sqrt{d_k}})K$

<br>

#### 5. Are the following statements true regarding Query (Q), Key (K) and Value (V)?
Q = interesting questions about the words in a sentence<br>
K = qualities of words given a Q<br>
V = specific representations of words given a Q<br>
- [x] **True**
- [ ] False

<br>

#### 6. $Attention(W_i^QQ,W_i^KK,W_i^VV)$
$i$ here represents the computed attention weight matrix associated with the ithith “word” in a sentence.

- [ ] True
- [x] **False**

> 📌 $i$ here represents the computed attention weight matrix associated with the $ith$ “head” (sequence).

<br>

#### 7. Following is the architecture within a Transformer Network (without displaying positional encoding and output layers(s)).
![image](https://user-images.githubusercontent.com/55765292/194751675-5d15a6bd-144e-4f2d-b9e1-a3bd26e4155a.png)

What is ***NOT*** necessary for the Decoder’s second block of Multi-Head Attention?

- [ ] K
- [ ] Q
- [ ] All of the above are necessary for the Decoder's second block.
- [ ] V

<br>

#### 8. Following is the architecture within a Transformer Network (without displaying positional encoding and output layers(s)).
![image](https://user-images.githubusercontent.com/55765292/194751742-71c02e32-05a8-4ad7-99f8-215e2b4b18e9.png)

The output of the decoder block contains a softmax layer followed by a linear layer to predict the next word one word at a time. 

- [ ] True
- [x] **False**

<br>

#### 9. Which of the following statements is true?
- [ ] The transformer network is similar to the attention model in that neither contain positional encoding.
- [ ] The transformer network is similar to the attention model in that both contain positional encoding.
- [x] **The transformer network differs from the attention model in that only the transformer network contains positional encoding.**
- [ ] The transformer network differs from the attention model in that only the attention model contains positional encoding.

> 📌 Positional encoding allows the transformer network to offer an additional benefit over the attention model.

<br>

#### 10. Which of these is ***not*** a good criterion for a good positional encoding algorithm?
- [x] **It should output a common encoding for each time-step (word's position in a sentence).**
- [ ] Destance between any two time-steps should be consistent for all sentence lengths.
- [ ] It must be deterministic.
- [ ] The algorithm should be able to generalize to longer sentences.

> 📌 This is not a good criterion for a good positional encoding algorithm.

<br>

#### 11. Which of the following statements is true about positional encoding? Select all that apply.
- [ ] Positional encoding is used in the transformer network and the attention model.
- [x] **Positional encoding provides extra information to our model.**
- [x] **Positional encoding uses a combination of sine and cosine equations.**
- [x] **Positional encoding is important because position and word order are essential in sentence construction of any language.**
