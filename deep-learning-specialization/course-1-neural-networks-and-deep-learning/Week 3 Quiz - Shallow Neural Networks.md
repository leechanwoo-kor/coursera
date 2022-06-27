## Week 3 Quiz - Shallow Neural Networks


### 1. Which of the following are true? (Check all that apply.)
- [ ] $W^{[1]}$ is a matrix with rows equal to the parameter vector of the first layer.
- [x] **$W^{[1]}$ is a matrix with rows equal to the transpose of the parameter vectors of the first layer**
- [ ] $a^{{[3]}(2)}$ denotes the activation vector of the second layer for the third example.
- [ ] $w_3^{[4]}$ is the column vector of parameters of the third layer and fourth neuron.
- [x] **$w_3^{[4]}$ is the column vector of parameters of the fourth layer and third neuron.**
<br>📌 The vector $w_j^{[i]}$ is the column vector of parameters of the i-th layer and j-th neuron of that layer.
- [x] **$a^{[2]}$ denotes the activation vector of the second layer**
<br>📌 In our convention $a^{[j]}$ denotes the activation function of the j-th layer.
- [ ] $a_3^{[2]}$ denotes the activation vector of the second layer for the third example.
- [ ] $w_3^{[4]}$ is the row vector of parameters of the fourth layer and third neuron.


### 2. The tanh activation is not always better than sigmoid activation function for hidden units because the mean of its output is closer to zero, and so it centers the data, making learning complex for the next layer. True/Flase?
- [ ] True
- [x] **Flase**
```
📌 The output of the tanh is between -1 and 1, it thus centers the data which makes the learning simpler for the next layer.
```

### 3. Which of these is a correct vectorized implementation of forward propagation for layer l, where 1 ≤ l ≤ L?
📌 $Z^{[l]} = W^{[l]}A^{[l-1]} + b^{[l]}$, $A^{[l]} = g^{[l]}(Z^{[l]})$


### 4. You are building a binary classifier for recognizing cucumbers (y=1) vs. watermelons (y=0). Which one of these activation functions would you recommend using for the output layer?
- [x] **sigmoid**
```
📌 Sigmoid outputs a value between 0 and 1 which makes it a very good choice for binary classification.
You can classify as 0 if the output is less than 0.5 and classify as 1 if the output is more than 0.5.
It can be done with tanh as well but it is less convenient as the output is between -1 and 1.
```
- [ ] ReLU
- [ ] Leaky ReLU
- [ ] tanh


### 5. Consider the following code:
```
x=np.random.rand(3,2)
y=np.sum(x,axis=0,keepdims=True)
```
**What will be y.shape?**
- [ ] (3,1)
- [ ] (3,)
- [x] **(1,2)**
- [ ] (2,)
```
📌 By choosing the axis=0 the sum is computed over each column of the array,
thus the resulting array is a row vector with 2 entries.
Since the option keepdims=True is used the first dimension is kept.
```


### 6. Suppose you have built a neural network. You decide to initialize the weights and biases to be zero. Which of the following statements is true?
- [ ] Each neuron in the first hidden layer will perform the same computation in the first iteration. But after one iteration of gradient descent they will learn to compute different things because we have "broken symmetry"
- [x] **Each neuron in the first hidden layer will perform the same computation. So even after multiple iterations of gradient descent each neuron in the layer will be computing the same thing as other neurons.**
- [ ] Each neuron in the first hidden layer will compute the same thing, but neurons in different layers will compute different things, thus we have accomplished “symmetry breaking” as described in lecture.
- [ ] The first hidden layer’s neurons will perform different computations from each other even in the first iteration; their parameters will thus keep evolving in their own way.


### 7. Logistic regression's weights should be initialized randomly rather than to all zeros, because if you initialize to all zeros, then logistic regression will fail to learn a useful decision boundary because it will fail to "break symmetry", True/False?
- [ ] True
- [x] **False**
```
📌 Logistic Regression doesn't have a hidden layer.
If you initialize the weights to zeros, the first example x fed in the logistic regression will output zero but the derivatives of the Logistic Regression depend on the input x (because there's no hidden layer) which is not zero.
So at the second iteration, the weights' values follow x's distribution and are different from each other if x is not a constant vector.
```


### 8. Which of the following is true about the ReLU activation functions?
- [ ] They cause several problems in practice because they have no derivative at 0. That is why Leaky ReLU was invented.
- [x] **They are the go to option when you don't know what activation function to choose for hidden layers.**
- [ ] They are increasingly being replaced by the tanh in most cases.
- [ ] They are only used in the case of regression problems, such as presicting house prices.


### 9. Consider the following 1 hidden layer neural network:

![image](https://user-images.githubusercontent.com/55765292/175864790-d92ee3a8-1c47-4bd8-875d-4d7a64af4c77.png)

**Which of the following statements are True? (Check all that apply).**

- [x] **$b^{[1]}$ will have shape (2, 1)**
- [ ] $b^{[1]}$ will have shape (4, 1)
- [x] **$W^{[2]}$ will have shape (1, 2)**
- [x] **$W^{[1]}$ will have shape (2, 4)**
- [ ] $W^{[1]}$ will have shape (4, 2)
- [ ] $W^{[2]}$ will have shape (2, 1)


### 10. Consider the following 1 hidden layer neural network:

![image](https://user-images.githubusercontent.com/55765292/175864790-d92ee3a8-1c47-4bd8-875d-4d7a64af4c77.png)

**What are the dimensions of $Z^{[1]}$ and $A^{[1]}$?

- [x] **$Z^{[1]}$ and $A^{[1]}$ are (2, m)**
- [ ] ...


```
📌 The $Z^{[1]}$ and $A^{[1]}$ are calculated over a batch of training examples.
The number of columns in  $Z^{[1]}$ and $A^{[1]}$ is equal to the number of examples in the batch, m.
And the number of rows in $Z^{[1]}$ and $A^{[1]}$ is equal to the number of neurons in the first layer.
```

### 11. The use of the ReLU activation function is becoming more rare because the ReLU function has no derivative for `c=0`. True/False?
- [ ] True
- [x] **False**

```
📌 Although the ReLU function has no derivative at `c = 0` this rarely causes any problems in practice.
Moreover it  has become the default activation function in many cases, as explained in the lectures.
```


### 12. Suppose you have built a beural network with one hidden layer and tanh as activation function for the hidden layers. Which of the following is a best option to initialize the weights?
- [ ] Initialize all weights to 0.
- [ ] Initialize the weights to large random numbers.
- [ ] Initialize all weights to a single number chosen randomly.
- [x] **Initialize the weights to small random numbers.**

```
📌 When using large numbers the values $z^{[k]}$ will be large and thus the activation will have small gradients making the training process slower.
```


### 13. A single output and single layer neural network that uses the sigmoid function as activation is equivalent to the logistic regression. True/False
- [ ] False
- [x] True

📌 The logistic regression model can be expressed by $\hat{y} = \sigma{(Wx+b)}$. this is the same as $a^{[1]} = \sigma{(W^{[1]}X+b)}$.


---

Prameters $W^{[l]}$ and $b^{[l]}$

![image](https://user-images.githubusercontent.com/55765292/175869369-5e348793-7d38-4f18-9981-eb7e9ad2dfb5.png)
