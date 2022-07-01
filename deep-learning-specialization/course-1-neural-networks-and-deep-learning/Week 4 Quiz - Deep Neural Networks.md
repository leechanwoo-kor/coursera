## Week 4 Quiz - Deep Neural Networks

### 1. We use the "cache" in our implementation of forward and backward propagation to pass useful values to the next layer in the forwar propergation. True/False?
- [ ] True
- [x] **False**
```
📌 The "cache" is used in our implementation to store values computed during forward propagation to be used in backward propagation.
```


### 2. Which of the following are "parameters" of a neural network? (Check all that apply.)
- [x] **$W^{[l]}$ the weight matrices**
- [x] **$b^{[l]}$ the bias vector.**
```
📌 The weight matrices and the bias vectors are the parameters of the network.
```
- [ ] $L$ the number of layers of the neural network.
- [ ] $g^{[l]}$ the activation functions.


### 3. Which of the following statements is true?
- [x] **The deeper layers of a neural network are typically computing more complex features of the input than the earlier layers.**
- [ ] The earlier layers of a neural network are typically computing more complex features of the input than the deeper layers.


### 4. We can not use vectorization to calculate $da^{[l]}$ in backpropagation, we must use a for loop over all the examples.
- [ ] True
- [x] **False**
```
📌 We can use vectorization in backpropagation to calculate $dA^{[l]}$ for each layer.
This computation is done over all the training examples.
```


### 5. Assume we store the values for $n^{[l]}$ in an array called layer_dims, as follows: layer_dims = [$n_xn$,4,3,2,1]. So layer 1 has four hidden units, layer 2 has 3 hidden units, and so on. Which of the following for-loop will allow you to initialize the parameters for the model?
- [x] **for i range(len(layer_dims)-1:<br>
      parameter['W' + str(i+1)] = np.random.randn(layer_dims[i], layer_dims[i+1]) * 0.01<br>
      parameter['b' + str(i+1)] = np.random.randn(layer_dims[i+1], 1) * 0.01**
- [ ] ...

📌 This iterates over 0, 1, 2, 3 and assigns to $W^{[l]}$ the shape ($n^{[l]}, n^{[l-1]}$).


### 6. Consider the following neural network:

![image](https://user-images.githubusercontent.com/55765292/176855405-99233139-6c8d-4292-b5a4-ae2b4c2888de.png)

**What are all the values of $n^{[0]},n^{[1]},n^{[2]},n^{[3]}$ and $n^{[4]}$?**
- [x] **4, 4, 3, 2, 1**
- [ ] ...

📌 The $n^{[l]}$ are the number of units in each layer, notice that $n^{[0]} = n_x$.


### 7. If L is the number of layers of a neural network then $dZ^{[L]} = A^{[L]} - Y$. True/False?
- [x] **True, The gradient of the output layer depends on the difference between the value computed during the forward propagation process and the target values.**
- [ ] False, The gradient of the output layer depends on the difference between the value computed during the forward propagation process and the target values.


### 8. There are certain functions with the following properties:
```
(i) to compute the function using a shallow network circuit, you will need a large network
(where we measure size by the number of logic gates in the network),
but (ii) To compute it using a deep network circuit,
you need only an exponentially smaller network. True/False?
```
- [x] **True**
- [ ] False


### 9. Consider the following 2 hidden layers neural network:

![image](https://user-images.githubusercontent.com/55765292/176856645-4e7d1eef-e170-4567-a685-7f02338187b6.png)

**Which of the following statements are true? (Check all the apply).**
- [x] **$W^{[2]}$ will have shape (4,3)**
- [ ] $W^{[2]}$ will have shape (3,1)
- [ ] $W^{[1]}$ will have shape (4,3)
- [x] **$W^{[1]}$ will have shape (3,4)**

📌 More generally, the shape of $W^{[l]}$ is ($n^{[l]}, n^{[l-1]}$).

- [ ] $W^{[2]}$ will have shape (3,4)
- [ ] $W^{[2]}$ will have shape (1,3)
- [ ] $b^{[1]}$ will have shape (1,3)
- [x] **$b^{[1]}$ will have shape (3,1)**

📌 More generally, the shape of $b^{[l]}$ is ($n^{[l]}, 1$).

- [ ] $b^{[1]}$ will have shape (4,1)


### 10. Whereas the previous question used a specific network, in the general case what is the dimension of $W^{[l]}$, the weight matrix associated with layer $l$?
- [x] **$W^{[l]}$ has shape ($n^{[l-1]}, n^{[l]}$)**
- [ ] ...
