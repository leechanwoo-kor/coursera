## Week 2 Quiz - Optimization Algorithms


### 1. Which notation would you use to denote the 4th layer's activations when the input is the 7th example from the 3rd mini-batch
- [x] **$a^{[4]\{3\}(7)}$**
- [ ] $a^{[7]\{3\}(4)}$
- [ ] $a^{[3]\{7\}(4)}$
```
📌 In general $a^{[l]\{t\}(k)}$ denotes the activation of the layer $l$ when the input is the example $k$ from the mini-batch $t$.
```


### 2. Which of these statements about mini-batch gradient descent do you agree with?
- [ ] You should implement mini-batch gradient descent without an explicit for-loop over different mini-batches, so that the algorithm processes all mini-batches at the same time (vectorization).
- [ ] Training one epoch (one pass through the training set) using mini-batch gradient descent is faster than training one epoch using batch gradient descent.
- [x] **One iteration of mini-batch gradient descent (computing on a single mini-batch) is faster than one iteration of batch gradient descent.**


### 3. Which of the following is true about batch gradient descent?
- [ ] It has as many mini-batches as examples in the training set.
- [ ] It is the same as stochastic gradient descent, but we don't use random elements
- [x] **It is the same as the mini-batch gradient descent when the mini-batch size is the same as the size of the training set.**
```
📌 When using batch gradient descent there is only one mini-batch thus it is equivalent to batch gradient descent.
```


### 4. While using mini-batch gradient descent with a batch size larger than 1 but less than m, the plot of the cost function $J$ looks like this:

![image](https://user-images.githubusercontent.com/55765292/178682791-1de71077-199d-4360-8c76-5b51ecec6dd5.png)

**You notice that the value of $J$ is not always decreasing. Which of the following is the most likely reason for that?**
- [ ] You are not implementing the moving averages correctly. Using moving averages will smooth the graph.
- [ ] The algorithm is on a local minimum thus the noisy behavior.
- [ ] A bad implementation of the backpropagation process, we should use gradient check to debug our implementation.
- [x] **In mini-batch gradient descent we calculate $J(\hat{y}^{\{t\}},y^{\{t\}})$ thus with each batch we compute over a new set of data.**
```
📌 Since at each iteration we work with a different set of data or batch the loss function doesn't have to be decreasing at each iteration.
```

### 4-1. Suppose your learning algorithm’s cost JJ, plotted as a function of the number of iterations, looks like this: [same image] Which of the following do you agree with?
- [ ] Whether you're using batch gradient descent or mini-batch gradient descent, this looks acceptable.
- [ ] Whether you're using batch gradient descent or mini-batch gradient descent, something is wrong.
- [ ] If you're using mini-batch gradient descent, something is wrong. But if you're using batch gradient descent, this looks acceptable.
- [x] **If you're using mini-batch gradient descent, this looks acceptable. But if you're using batch gradient descent, something is wrong.**

### 5. Suppose the temperature in Casablanca over the first two days of March are the following:

**March 1st: $\theta_1 = 30^{\circ}C$**

**March 2nd: $\theta_2 = 15^{\circ}C$**

**Say you use an exponentially weighted average with $\beta = 0.5$ to track the temperature: $v_0 = 0, v_t = \beta v_{t-1} + (1- \beta) \theta_t$. If $v_2$ is the value computed after day 2 without bias correction, and $v_2^{\text{corrected}}$ is the value you compute with bias correction. What are these values?**

- [ ] $v_2 = 15, v_2^{\text{corrected}} = 15$.
- [x] **$v_2 = 15, v_2^{\text{corrected}} = 20$.**
- [ ] $v_2 = 20, v_2^{\text{corrected}} = 20$.
- [ ] $v_2 = 20, v_2^{\text{corrected}} = 15$.
```
📌 v_2 = β v_{t−1} + (1−β) θ_t thus v_1 = 15, v_2 = 15. Using the bias correction v_t/1−β_t we get 15/1−(0.5)^2 = 20.
```


### 6. Which of the following is true about learning rate decay?
- [x] **The intuition behind it is that for later epochs our parameters are closer to a minimum thus it is more convenient to take smaller steps to prevent large oscillations.**
- [ ] It helps to reduce the variance of a model.
- [ ] The intuition behind it is that for later epochs our parameters are closer to a minimum thus it is more convenient to take larger steps to accelerate the convergence.
- [ ] We use it to increase the size of the steps taken in each mini-batch iteration.
```
📌 Reducing the learning rate with time reduces the oscillation around a minimum.
```


### 7. You use an exponentially weighted average on the London temperature dataset. You use the following to track the temperature: $v_{t} = \beta v_{t-1} + (1-\beta)\theta_t$. The yellow and red lines were computed using values $\beta_1$ and $\beta_2$ respectively. Which of the following are true?
- [x] **$\beta_1 > \beta_2$**.
- [ ] ...


### 8. Which of the following are true about gradient descent with momentum?
- [ ] It decreases the learning rate as the number of epochs increases.
- [ ] Gradient descent with momentum makes use of moving averages.
- [ ] Increasing the hyperparameter $\beta$ smooths out the process of gradient descent.
- [x] **It generates faster learning by reducing the oscillation of the gradient descent process.**
```
📌 The use of momentum makes each step of the gradient descent more efficient by reducing oscillations.
```


### 9. Suppose batch gradient descent in a deep network is taking excessively long to find a value of the parameters that achieves a small value for the cost function $\mathcal{J}(W^{[1]},b^{[1]},...,W^{[L]},b^{[L]})$. Which of the following techniques could help find parameter values that attain a small value for $\mathcal{J}$? (Check all that apply)
- [x] **Try using gradient descent with momentum.**
```
📌 The use of momentum can improve the speed of the training. Although other methods might give better results, such as Adam.
```
- [x] **Try mini-batch gradient descent.**
```
📌 Mini-batch gradient descent is faster than batch gradient descent.
```
- [x] **Try using Adam.**
```
📌 Adam combines the advantages of other methods to accelerate the convergence of the gradient descent.
```
- [ ] Try initailzing the weight at zero.
- [ ] Try better random initialization for the weights.
- [ ] Add more data to the training set.
- [x] **Normalize the input data.** 
```
📌 In some cases, if the scale of the features is very different, normalizing the input data will speed up the training process.
```


### 10. In very high dimensional spaces it is most likely that the gradient descent process gives us a local minimum than a saddle point of the cost function. True/False?
- [ ] True
- [x] **False**
```
📌 Due to the high number of dimensions it is much more likely to reach a saddle point, than a local minimum.
```


### 11. Which of these is NOT a good learning rate decay scheme? Here, t is the epoch number.
- [ ] $\alpha = \dfrac{1}{1 + 2 * t} \alpha_0$
- [ ] $\alpha = 0.95^t \alpha_0$
- [ ] $\alpha = \dfrac{1}{\sqrt{t}} \alpha_0$
- [x] $\alpha = e^t \alpha_0$$


### 12. Consider this figure:

![image](https://user-images.githubusercontent.com/55765292/178691789-764cf300-7255-4710-8b25-9782b77257fd.png)

**These plots were generated with gradient descent; with gradient descent with momentum (β = 0.5); and gradient descent with momentum (β = 0.9). Which curve corresponds to which algorithm?**
- [x] (1) is gradient descent. (2) is gradient descent with momentum (small β). (3) is gradient descent with momentum (large β).
- [ ] ...



### 12. Which of the following statements about Adam is False?
- [x] **Adam should be used with batch gradient computation, not with mini-batches.**
- [ ] ...
