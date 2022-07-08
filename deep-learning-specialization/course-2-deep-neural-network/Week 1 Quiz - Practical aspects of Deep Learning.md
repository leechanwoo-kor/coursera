## Week 1 Quiz - Practical aspects of Deep Learning


### 1. If you have 20,000,000 examples, how would you split the train/dev/test set? Choose the best option.
- [ ] 60% train. 20% dev. 20% test.
- [ ] 90% train. 5% dev. 5% test.
- [x] 99% train. 0.5% dev. 0.5% test.
```
📌 This might be considered adequate with a small data set not in the range of bigdata,
but it is not adequate for a dataset of the given size.
```


### 2. In a personal experiment, an M.L. student decides to not use a test set, only train-dev sets. In this case which of the following is true?
- [ ] Not having a test set is unacceptable under any circumstance.
- [x] **He might be overfitting to the dev set.**
- [ ] He won't be able to measure the variance of the model.
- [ ] He won't be able to measure the bias of the model.
```
📌 Although not recommended, if a more accurate measure of the performance is not necessary it is ok to not use a test set.
However, this might cause an overfit to the dev set.
```


### 3. A model developed for a project is presenting high bias. One of the sponsors of the project offers some resources that might help reduce the bias. Which of the following additional resources has a better chance to help reduce the bias?
- [ ] Use different sources to gather data and better test the model.
- [ ] Gather more data for the project.
- [ ] Give access to more computational resources like GPUs.


### 4. You are working on an automated check-out kiosk for a supermarket, and are building a classifier for apples, bananas and oranges. Suppose your classifier obtains a training set error of 0.5%, and a dev set error of 7%. Which of the following are promising things to try to improve your classifier? (Check all that apply.)
- [x] **Increase the regularization parameter lambda**
- [ ] Decrease the regularization parameter lambda.
- [x] **Get more training data.**
- [ ] Use a bigger neural network.


### 5. In every case it is a good practice to use dropout when training a deep neural network because it can help to prevent overfitting. True/False?
- [ ] True
- [x] **False**
```
📌 In most cases, it is recommended to not use dropout if there is no overfit.
Although in computer vision, due to the nature of the data, it is the default practice.
```


### 6. To reduce high variance, the regularization hyperparameter lambda must be increased. True/False?
- [x] **True**
```
📌 By increasing the regularization parameter the magnitude of the weight parameters is reduced.
This helps reduce the variance.
```
- [ ] False


### 7. Which of the following are true about dropout?
- [ ] In practice, it eliminates units of each layer with a probability of keep_prob.
- [ ] In practice, it eliminates units of each layer with a probability of 1-keep_prob.
- [ ] It helps to reduce the bias of a model.
- [x] **It helps to reduce overfitting.**


### 8. Decreasing the parameter keep_prob from (say) 0.6 to 0.4 will likely cause the following:
- [ ] Reducing the regularization effect.
- [ ] Causing the neural network to have a higher variance.
- [x] **Increasing the regularization effect.**
```
📌 This will make the dropout have a higher probability of eliminating a node in the neural network,
increasing the regularization effect.
```


### 9. Which of these techniques are useful for reducing variance (reducing overfitting)? (Check all that apply.)
- [ ] Exploding gradient
- [ ] Vanishing gradient
- [ ] Gradient Checking
- [ ] Xavier initialization
- [x] **Dropout**
- [x] **Data augmentation**
- [x] **L2 regularization**


### 10. Which of the following is the correct expression to normalize the input $x$?
- [x] **$x = \cfrac{x - \mu}{\sigma}$**
- [ ] ...
```
📌 This shifts the mean of the input to the origin and makes the variance one in each coordinate of the input examples.
```
