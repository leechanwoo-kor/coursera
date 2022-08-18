## Week 2 Quiz - Deep Convolutional Models

### 1. When building a ConvNet, typically you start with some POOL layers followed by some CONV layers. True/False?
- [ ] True
- [x] **False**
> 📌 It is typical for ConvNets to use a POOL layer after some Conv layers; sometimes even one POOL layer after each CONV layer; but is not common to start with POOL layers.

### 2. In LeNet - 5 we can see that as we get into deeper networks the number of channels increases while the height and width of the volume decreases. True/False?
- [x] **True**
- [ ] False
> 📌 Since in its implementation only valid convolutions were used, without padding, the height and width of the volume were reduced at each convolution. These were also reduced by the POOL layers, whereas the number of channels was increased from 6 to 16.

### 3. Training a deeper network (for example, adding additional layers to the network) allows the network to fit more complex functions and thus almost always results in lower training error. For this question, assume we’re referring to “plain” networks.
- [ ] True
- [x] **False**
> 📌 Resnets are here to help us train very deep neural networks.

### 4. Which of the following equations captures the computations in a ResNet block?
- [x] $a^{[l+2]} = g(W^{[l+2]}g(W^{[l+1]}a^{[l]} + b^{[l+1]}) + b^{[l+2]} + a^{[l]})$
- [ ] ...
> 📌 This expresses the computations of a ResNet block, where the last term $a^{[l]}$ is the shortcut connection.

### 5. Adding a ResNet block to the end of a network makes it deeper. Which of the following is true?
- [ ] The number of parameters will decrease due to the shortcut connections.
- [ ] It shifts the behavior of the network to be more like the identity function.
- [ ] The performance of the networks is hurt since we make the network harder to train.
- [ ] The performance of the networks doesn't get hurt since the ResNet block can easily approximate the identity function.

### 6. For a volume of $125 \times 125 \times 64$ which of the following can be used to reduce this to a $125 \times 125 \times 32$ volume?
- [ ] Use a POOL layer of size $2 \times 2$ with a stride of 2.
- [ ] Use a $1 \times 1$ convolutional layer with a stride of 2, and 32 filters.
- [x] **Use a $1 \times 1$ convolutional layer with a stride of 1, and 32 filters.**
- [ ] Use a POOL layer of size $2 \times 2$ but with a stride of 1.
> 📌 Since using $1 \times 1$ convolutions is a great way to reduce the depth dimension without affecting the other dimensions.


### 7. Which ones of the following statements on Inception Networks are true? (Check all that apply.)
- [ ] Making an inception network deeper (by stacking more inception blocks together) might not hurt training set performance.
- [ ] Inception networks incorporate a variety of network architectures (similar to dropout, which randomly chooses a network architecture on each step) and thus has a similar regularizing effect as dropout.
- [x] **A single inception block allows the network to use a combination of $1 \times 1, 3 \times 3, 5 \times 5$ convolutions and pooling.**
- [x] **Inception blocks usually use $1 \times 1$ convolutions to reduce the input data volume's size before applying $3 \times 3$ and $5 \times 5$ convolutions.**

### 8. When having a small training set to construct a classification model, which of the following is a strategy of transfer learning that you would use to build the model?
- [ ] Use an open-source network trained in a larger dataset, freeze the softmax layer, and re-train the rest of the layers.
- [ ] It is always better to train a network from a random initialization to prevent bias in our model.
- [ ] Use an open-source network trained in a larger dataset. Use these weights as an initial point for the training of the whole network.
- [ ] Use an open-source network trained in a larger dataset freezing the layers and re-train the softmax layer.

### 9. Which of the following are true about Depth wise-separable convolutions? (Choose all that apply)
- [x] **They have a lower computational cost than normal convolutions.**
> 📌 As seen in the lectures the use of the depthwise and pointwise convolution reduces the computational cost significantly.
- [ ] The result has always the same number of channels $n_c$ as the input.
- [x] **They combine depthwise convolutions with pointwise convolutions.**
> 📌 This combination is what we call depth wise separable convolutions.
- [ ] They are just a combination of a normal convolution and a bottleneck layer.

### 10. Fill in the missing dimensions shown in the image below (marked W, Y, Z).
![image](https://user-images.githubusercontent.com/55765292/185272892-912682e9-7d62-4dd0-88c2-2c011788e1ef.png)
- [x] **W = 5, Y = 30, Z = 20**
- [ ] ...
