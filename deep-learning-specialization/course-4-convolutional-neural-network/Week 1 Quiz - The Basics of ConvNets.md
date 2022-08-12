## Week 1 Quiz - The Basics of ConvNets


### 1. What do you think applying this filter to a grayscale image will do?

![image](https://user-images.githubusercontent.com/55765292/184266950-9d72c82e-0ea3-4017-a395-3380797ba042.png)

- [ ] Detect vertical edges.
- [x] **Detect 45-degree edges.**
- [ ] Detecting image contrast.
- [ ] Detect horizontal edges. 

> 📌 Notice that there is a high delta between the values in the top left part and the ones in the bottom right part. When convolving this filter on a grayscale image, the edges forming a 45-degree angle with the horizontal will be detected.


### 2. Suppose your input is a 128 by 128 grayscale image, and you are not using a convolutional network. If the first hidden layer has 256 neurons, each one fully connected to the input, how many parameters does this hidden layer have (including the bias parameters)?

- [ ] 4194304
- [ ] 12583168
- [ ] 12582912
- [ ] 4194560


### 3. Suppose your input is a 300 by 300 color (RGB) image, and you use a convolutional layer with 100 filters that are each 5x5. How many parameters does this hidden layer have (including the bias parameters)?

- [ ] 2501
- [x] **7600**
- [ ] 7500
- [ ] 2600

> 📌 you have $25 \times 3 = 75$ weights and $1$ bias per filter. Given that you have 100 filters, you get 7,600 parameters for this layer.


### 4. You have an input volume that is $127 \times 127 \times 16$, and convolve it with 32 filters of $5 \times 5$, using a stride of 2 and no padding. What is the output volume?

- [ ] $123 \times 123 \times 32$
- [ ] $123 \times 123 \times 16$
- [ ] $62 \times 62 \times 16$
- [x] **$62 \times 62 \times 32$**

> 📌 Using the formula $n_H^{[l]} = \dfrac{n_H^{[l−1]} + 2 \times p − f}{s} + 1$ with $n_H^{[l−1]} = 127, p = 0, f = 5, and s = 2$ we get 62.


### 5. You have an input volume that is $31 \times 31 \times 32$, and pad it using “pad=1”. What is the dimension of the resulting volume (after padding)?

- [ ] $31 \times 31 \times 34$
- [x] **$33 \times 33 \times 32$**
- [ ] $33 \times 33 \times 33$
- [ ] $32 \times 32 \times 32$

> 📌 If the padding is 1 you add 2 to the height dimension and 2 to the width dimension.


### 6. You have a volume that is $121 \times 121 \times 32$, and convolve it with 32 filters of $5\times 5$, and a stride of 1. You want to use a "same" convolution. What is the padding?

- [x] **2**
- [ ] 3
- [ ] 5
- [ ] 0

> 📌 When using a padding of 2 the output volume has $n_H = \dfrac{121−5+4}{1}+1$.


### 7. You have an input volume that is $128 \times 128 \times 12$, and apply max pooling with a stride of 4 and a filter size of 4. What is the output volume?

- [x] **$32 \times 32 \times 12$**
- [ ] $128 \times 128 \times 3$
- [ ] $32 \times 32 \times 3$
- [ ] $64 \times 64 \times 12$

> 📌 Using the formula $n_H^{[l]} = \dfrac{n_H^{[l−1]} + 2 \times p − f}{s} + 1$ with $p=0, f=4, s=4$ and $n_H^{[l−1]} = 32$.


### 8. Because pooling layers do not have parameters, they do not affect the backpropagation (derivatives) calculation.

- [ ] True
- [x] **False**

> 📌 Everything that influences the loss should appear in the backpropagation because we are computing derivatives. In fact, pooling layers modify the input by choosing one value out of several values in their input volume. Also, to compute derivatives for the layers that have parameters (Convolutions, Fully-Connected), we still need to backpropagate the gradient through the Pooling layers.


### 9. Which of the following are true about convolutional layers? (Check all that apply)

- [ ] It allows parameters learned for one task to be shared even for a different task (transfer learning).
- [ ] It speeds up the training since we don't need to compute the gradient for convolutional layers.
- [x] **Convolutional layers provide sparsity of connections.**
> 📌 This happens since the next activation layer depends only on a small number of activations from the previous layer.
- [x] **It allows a feature detector to be used in multiple locations throughout the whole input volume.**
> 📌 Since convolution involves sliding the filter throughout the whole input volume the feature detector is computed over all the volume.


### 10. The following image depicts the result of a convolution at the right when using a stride of 1 and the filter is shown right next.

![image](https://user-images.githubusercontent.com/55765292/184268185-4c5547c9-e173-4f7c-96ea-1663f62937d0.png)

**On which pixels does the circled pixel of the activation at the right depend?**

- [x] **It depends on the pixels enclosed by the green square.**
- [ ] ...

> 📌 this is the position of the filter when we move it two pixels down and one to the right.
