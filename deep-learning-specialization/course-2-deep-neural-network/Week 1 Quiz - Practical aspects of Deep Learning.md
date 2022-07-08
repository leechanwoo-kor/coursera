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
- [x] **Give access to more computational resources like GPUs.**
```
📌 More test data won't help reduce the bias.
```


### 4. You are working on an automated check-out kiosk for a supermarket, and are building a classifier for apples, bananas and oranges. Suppose your classifier obtains a training set error of 0.5%, and a dev set error of 7%. Which of the following are promising things to try to improve your classifier? (Check all that apply.)
- [x] **Increase the regularization parameter lambda**
- [ ] Decrease the regularization parameter lambda.
- [x] **Get more training data.**
- [ ] Use a bigger neural network.

### 4-1. You are working on an automated check-out kiosk for a supermarket and are building a classifier for apples, bananas, and oranges. Suppose your classifier obtains a training set error of 19% and a dev set error of 21%. Which of the following are promising things to try to improve your classifier? (Check all that apply, suppose the human error is approximately 0%)
- [ ] Increase the regularization parameter lambda
- [ ] Decrease the regularization parameter lambda.
- [ ] Get more training data.
- [x] **Use a bigger network.**
```
📌 This can be helpful to reduce the bias of the model, 
and then we can start trying to reduce the high variance if this happens.
```


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
- [x] **It helps to reduce the variance of a model.**
- [x] **It helps to reduce overfitting.**


### 8. Decreasing the parameter keep_prob from (say) 0.6 to 0.4 will likely cause the following:
- [ ] Reducing the regularization effect.
- [ ] Causing the neural network to have a higher variance.
- [x] **Increasing the regularization effect.**
```
📌 This will make the dropout have a higher probability of eliminating a node in the neural network,
increasing the regularization effect.
```

### 8-1. Increasing the parameter keep_prob from (say) 0.5 to 0.6 will likely cause the following: (Check the two that apply)
- [ ] Increasing the regularization effect.
- [x] **Reducing the regularization effect.**
- [ ] Causing the neural network to end up with a higher training set error.
- [x] **Causing the neural network to end up with a lower training set error.**


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


### 11. When designing a neural network to detect if a house cat is present in the picture, 500,000 pictures of cats were taken by their owners. These are used to make the training, dev and test sets. It is decided that to increase the size of the test set, 10,000 new images of cats taken from security cameras are going to be used in the test set. Which of the following is true?
- [ ] This will increase the bias of the model so the new images shouldn't be used.
- [x] **This will be harmful to the project since now dev and test sets have different distributions.**
- [ ] This will reduce the bias of the model and help improve it.
```
📌 This won't have a real effect on the bias of the model but will hinder the way we are measuring the performance.
```


### 12. What is weight decay?
- [x] **A regularization technique (such as L2 regularization) that result in gradient descent shrinking the weights on every iteration.**
- [ ] Gradual corruption of the weights in the neural network if it is trained on noisy data.
- [ ] The process of gradually decreasing the learning rate during training.
- [ ] A technique to avoid vanishing gradient by imposing a ceiling on the values of the weights.


### 13. What happens when you increase the regularization hyperparameter lambda?
- [ ] Doubling lambda should roughly result in doubling the weights.
- [x] **Weights are pushed toward becoming smaller (closer to 0)**
- [ ] Weights are pushed toward becoming bigger (further from 0)
- [ ] Gradient descent taking bigger steps with each iteration (proportional to lambda)


### 14. During training a deep neural network that uses the tanh activation function, the value of the gradients is practically zero. Which of the following is most likely to help the vanishing gradient problem?
- [ ] Increase the number of layers of the network.
- [ ] Use a larger regularization parameter.
- [ ] Increase the number of cycles during the training.
- [x] **Use Xavier initialization.**
```
📌 A careful initialization can help reduce the vanishing gradient problem.
```


### 15 .Which of the following actions increase the regularization of a model? (Check all that apply)
- [ ] Use Xavier initialization.
- [ ] Increase the value of keep_prob in dropout.
- [x] **Decrease the value of keep_prob in dropout.**
- [x] **Increase the value of the hyperparameter lambda.**
- [ ] Decrease the value of the hyperparameter lambda.


### 16. If your Neural Network model seems to have high variance, what of the following would be promising things to try?
- [ ] Increase the number of units in each hidden layer
- [x] **Get more training data**
- [x] **Add regularization**
- [ ] Make the Neural Network deeper
- [ ] Get more test data


### 17. With the inverted dropout technique, at test time:
- [ ] You apply dropout (randomly eliminating units) and do not keep the 1/keep_prob factor in the calculations used in training.
- [ ] You apply dropout (randomly eliminating units) but keep the 1/keep_prob factor in the calculations used in training.
- [x] **You do not apply dropout (do not randomly eliminate units) and do not keep the 1/keep_prob factor in the calculations used in training.**
- [ ] You do not apply dropout (do not randomly eliminate units), but keep the 1/keep_prob factor in the calculations used in training.


### 18. Suppose that a model uses, as one feature, the total number of kilometers walked by a person during a year, and another feature is the height of the person in meters. What is the most likely effect of normalization of the input data?
- [ ] It will make the data easier to visualize.
- [ ] It won't have any positive or negative effects.
- [ ] It will increase the variance of the model.
- [ ] It will make the training faster.
```
📌 It doesn't affect the visualization of the data,
although in the 2 or 3 dimensions the dispersion plots look different.
```
