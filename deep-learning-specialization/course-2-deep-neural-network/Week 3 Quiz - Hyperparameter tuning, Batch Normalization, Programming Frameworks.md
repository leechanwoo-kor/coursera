## Week 3 Quiz - Hyperparameter tuning, Batch Normalization, Programming Frameworks


### 1. If searching among a large number of hyperparameters, you should try values in a grid rather than random values, so that you can carry out the search more systematically and not rely on chance. True or False?
- [ ] True
- [x] **False**


### 2. If it is only possible to tune two parameters from the following due to limited computational resources. Which two would you choose?
- [x] **$\alpha$**
> 📌 This might be the hyperparameter that most impacts the results of a model.
- [x] **The $\beta$ parameter of the momentum in gradient descent.**
> 📌 This hyperparameter can increase the speed of convergence of the training, thus is worth tuning.
- [ ] $\beta_1,\beta_2$ in Adam.
- [ ] $\epsilon$ in Adam.


### 3. Even if enough computational power is available for hyperparameter tuning, it is always better to babysit one model ("Panda" strategy), since this will result in a more custom model. True/False?
- [ ] True
- [x] **False**
> 📌 Although it is possible to create good models using the "Panda" strategy,
obtaining better results is more likely using a "caviar" strategy due to the number of tests and the nature of the deep learning process of ideas, code, and experiment.


### 4. If you think \betaβ (hyperparameter for momentum) is between 0.9 and 0.99, which of the following is the recommended way to sample a value for beta?
- [x] **r = np.random.rand()<br>beta = 1 - 10 \*\* (- r - 1)**
- [ ] ...


### 5. Once good values of hyperparameters have been found, those values should be changed if new data is added or a change in computational power occurs. True/False?
- [x] **True**
- [ ] False
> 📌 The choice of some hyperparameters such as the batch size, depends on conditions such as hardware and quantity of data.


### 6. When using batch normalization it is OK to drop the parameter $b^{[l]}$ from the forward propagation since it will be subtracted out when we compute $\tilde{z}^{[l]}_{\text{normalize}} = \beta^{[l]}\hat{z}^{[l]} + \gamma^{[l]}$. True/False?
- [x] **True**
- [ ] False
> 📌 Since in the normalization process the values of $z^{[l]}$ are re-centered at the origin, it is irrelevant to add the $b^{[l]}$ parameter.


### 7. In the normalization formula $z_{norm}^{(i)} = \frac{z^{(i)} - \mu}{\sqrt{\sigma^2 + \varepsilon}}$ , why do we use epsilon?
- [ ] In case $\mu$ is too small
- [ ] To speed up convergence
- [ ] To have a more accurate normalization
- [x] **To aviod division by zero**


### 8. Which of the following is true about batch normalization?
- [x] **The parameters $\gamma^{[l]}$ and $\beta^{[l]}$ set the mean and variance of $\bar{z}^{[l]}$.**
- [ ] $z_{norm}^{(i)} = \dfrac{z^{(i)} - \mu}{\sqrt{\sigma^2}}$
- [ ] The parameters $\gamma^{[l]}$ and $\beta^{[l]}$ can be learned only using gain gradient descent.
- [ ] The optimal values to use for $\gamma^{[l]}$ and $\beta^{[l]}$ are $\gamma^{[l]}=\sqrt{\sigma^2 + \varepsilon}$ and $\beta^{[l]}=\mu$


### 9. After training a neural network with Batch Norm, at test time, to evaluate the neural network on a new example you should:
- [ ] If you implemented Batch Norm on mini-batches of (say) 256 examples, then to evaluate on one test example, duplicate that example 256 times so that you're working with a mini-batch the same size as during training.
- [ ] Use the most recent mini-batch's values of $\mu$ and $\sigma^2$ to perform the needed normalizations.
- [ ] Skip the step where you normalize using $\mu$ and $\sigma^2$ since a single test example cannot be normalized.
- [x] **Perform the needed normalizations, use $\mu$ and $\sigma^2$ estimated using an exponentially weighted average across mini-batches seen during training.** 


### 10. If a project is open-source, it is a guarantee that it will remain open source in the long run and will never be modified to benefit only one company. True/False?
- [ ] True
- [x] **False**
> 📌 To ensure that a project will remain open source in the long run it must have a good governance body too.
