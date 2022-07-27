## Week 1 Case Study - Bird Recognition in the City of Peacetopia


### 1. Problem Statement
This example is adapted from a real production application, but with details disguised to protect confidentiality.

You are a famous researcher in the City of Peacetopia. The people of Peacetopia have a common characteristic: they are afraid of birds. To save them, you have **to build an algorithm that will detect any bird flying over Peacetopia** and alert the population.

The City Council gives you a dataset of 10,000,000 images of the sky above Peacetopia, taken from the city’s security cameras. They are labeled:

- y = 0: There is no bird on the image
- y = 1: There is a bird on the image

Your goal is to build an algorithm able to classify new images taken by security cameras from Peacetopia.

There are a lot of decisions to make:

- What is the evaluation metric?
- How do you structure your data into train/dev/test sets?

**Metric of success**

The City Council tells you the following that they want an algorithm that

1. Has high accuracy.
2. Runs quickly and takes only a short time to classify a new image.
3. Can fit in a small amount of memory, so that it can run in a small processor that the city will attach to many different security cameras.

You are delighted because this list of criteria will speed development and provide guidance on how to evaluate two different algorithms. True/False?

- [ ] True
- [x] **False**

> 📌 More than one metric expands the choices and tradeoffs you have to decide for each with unknown effects on the other two.

### 1-1. You meet with them and ask for just one evaluation metric. True/False?
- [ ] True
- [x] **False**


### 2. The city revises its criteria to:

- "We **need** an algorithm that can let us know a bird is flying over Peacetopia as accurately as possible."
- "We want the trained model to take no more than 10 sec to classify a new image.”
- “We want the model to fit in 10MB of memory.”

Given models with different accuracies, runtimes, and memory sizes, how would you choose one?

- [ ] Create one metric by combining the three metrics and choose the best performing model.
- [ ] Accuracy is an optimizing metric, therefore the most accurate model.
- [ ] Take the model with the smallest runtime because that will provide the most overhead to increase accuracy.
- [ ] Find the subset of models that meet the runtime and memory criteria. Then, choose the highest accuracy.

> 📌 You must still meet the thresholds for runtime and memory.
> 📌 Because we don’t care how much a model minimizes runtime and memory under 10s and 10MB respectively, this method is not valid.


### 3. Based on the city’s requests, which of the following would you say is true?

- [ ] Accuracy is a satisfying metric; running time and memory size are an optimizing metric.
- [ ] Accuracy, running time and memory size are all optimizing metrics because you want to do well on all three.
- [ ] Accuracy, running time and memory size are all satisfying metrics because you have to do sufficiently well on all three for your system to be acceptable.
- [x] **Accuracy is an optimizing metric; running time and memory size are satisfying metrics.**


### 4. With 10,000,000 data points, what is the best option for train/dev/test splits?

- [x] **train - 95%, dev - 2.5%, test - 2.5%**
- [ ] ...

> 📌 The size of the data set allows for bias and variance evaluation with smaller data sets.


### 5. Now that you’ve set up your train/dev/test sets, the City Council comes across another 1,000,000 images from social media and offers them to you. These images are different from the distribution of images the City Council had originally given you, but you think it could help your algorithm. Which of the following is the best use of that additional data?

- [ ] Do not use the data. It will change the distribution of any set it is added to.
- [ ] Split it among train/dev/test equally.
- [ ] Add it to the dev set to evaluate how well the model generalizes across a broader set.
- [x] **Add it to the training set.**

> 📌 It is not a problem to have different training and dev distributions. Different dev and test distributions would be an issue.


### 6. One member of the City Council knows a little about machine learning and thinks you should add the 1,000,000 citizens’ data images proportionately to the train/dev/test sets. You object because:

- [ ] The 1,000,000 citizens' data images do not have a consistent x-->y mapping as the rest of the data.
- [ ] A bigger test set will slow down the speed of iterating because of the computational expense of evaluating models on the test set.
- [ ] The additional data would significantly slow down training time.
- [ ] The training set will ent be as accurate because of the different distributions.
- [x] **If we add the images to the test set then it won't reflect the distribution of data expected in production.**
- [x] **This would cause the dev and test set distributions to become different. This is a bad idea because you're not aiming where you wnat to hit.**
- [x] **The test set no longer reflects the distribution of data(security cameras) you most care about.** 

> 📌 Using the data in the training set could be beneficial, but you wouldn't want to include such images in your test set as they are not from the expected distribution of data you'll see in production.


### 7. Human performance for identifying birds is < 1%, training set error is 5.2% and dev set error is 7.3%. Which of the options below is the best next step?

- [ ] Get more data or apply regularization to reduce variance.
- [ ] Try an ensemble model to reduce bias and variance.
- [x] **Train a bigger network to drive down the > 4.0% training error.**
- [ ] Validate the human data set with a sample of your data to ensure the images are of sufficient quality.

> 📌 Avoidable bias is >4.2% which is larger than the 2.1% variance.


### 8. You want to define what human-level performance is to the city council. Which of the following is the best answer?

- [ ] The average performance of all their ornithologists (0.5%).
- [ ] The average of regular citizens of Peacetopia (1.2%).
- [ ] The average of all the numbers above (0.66%).
- [x] **The performance of their best ornithologist (0.3%).**

> 📌 The best human performance is closest to Bayes' error.


### 9. Which of the below shows the optimal order of accuracy from worst to best?

- [x] **Human-level performance -> the learning algorithm's performance -> Bayes error.**
- [ ] ...

> 📌 A learning algorithm’s performance can be better than human-level performance but it can never be better than Bayes error.


### 10. Which of the following best expresses how to evaluate the next steps in your project when your results for human-level performance, train, and dev set error are 0.1%, 2.0%, and 2.1% respectively?

- [ ] Based on differences between the three levels of performance, prioritize actions to decrease bias and iterate.
- [ ] Evaluate the test set to determine the magnitude of the variance.
- [ ] Keep tuning until the train set accuracy is equal to human-level performance because it is the optimizing metric.
- [ ] Port the code to the target devices to evaluate if your model meets or exceeds the satisficing metrics.

> 📌 Always choose the area with the biggest opportunity for improvement.


### 11. You've now also run your model on the test set and find that it is a 7.0% error compared to a 2.1% error for the dev set. What should you do? (Choose all that apply)

- [ ] Increase the size of the dev set.
- [ ] Try decreasing regularization for better generalization with the dev set.
- [x] **Try increasing regularization to reduce overfitting to the dev set.**
- [ ] Get a bigger test set to increase its accuracy.


### 12. After working on this project for a year, you finally achieve: Human-level performance, 0.10%, Training set error, 0.05%, Dev set error, 0.05%. Which of the following are likely? (Check all that apply.)

- [x] **The model has recognized emergent features that humans cannot. (Chess and Go for example)**

> 📌 When Google beat the world Go champion, it was recognized that it was making deeper moves than humans.

- [ ] This result is not possible since it should not be possible to surpass human-level performance.
- [ ] There is still avoidable bias.
- [x] **Pushing to even higher accuracy will be slow because you will not be able to easily identify sources of bias.**

> 📌 Exceeding human performance means you are close to Bayes error.


### 12-1. After working on your algorithm you have to decide the next steps. Currently, human-level performance is 0.1%, training is at 2.0% and the dev set is at 2.1%. Which statement below best describes your thought process?

- [ ] Get a bigger training set to reduce variance.
- [ ] Decrease variance via regularization so training and dev sets have similar performance.
- [x] **Decrease regularization to boost smaller signals.**
- [x] **Address bias first through a larger model to get closet to human level error.**

> 📌 Selecting the largest difference from (train set error - human level error) and (dev set error - train set error) and reducing bias or variance accordingly is the most productive step.


### 13. Your system is now very accurate but has a higher false negative rate than the City Council of Peacetopia would like. What is your best next step?
- [ ] Look at all the models you've developed during the development process and find the one with the lowest false negative error rate.
- [ ] Expand your model size to account for more corner cases.
- [x] **Reset your "target" (matric) for the team and tune to it.**
- [ ] Pick false negative rate as the new metric, and use this new metric to drive all further development.

> 📌 The target has shifted so an updated metric is required.


### 14. You’ve handily beaten your competitor, and your system is now deployed in Peacetopia and is protecting the citizens from birds! But over the last few months, a new species of bird has been slowly migrating into the area, so the performance of your system slowly degrades because your data is being tested on a new type of data.

![image](https://user-images.githubusercontent.com/55765292/181160239-08d89860-53e3-4f51-b788-15d4b0e5c510.png)

You have only 1,000 images of the new species of bird. The city expects a better system from you within the next 3 months. Which of these should you do first?

- [ ] Put the 1,000 images into the training set so as to try to do better on these birds.
- [ ] Try data augmentation/data synthesis to get more images of the new type of bird.
- [ ] Add the 1,000 images into your dataset and reshuffle into a new train/dev/test split.
- [x] **Use the data you have to define a new evaluation metric (using a new dev/test set) taking into account the new species, and use that to drive further progress for your team.**

> 📌 The true data distribution is changed. It means you need to adjust your evaluation. Because you evaluate your learning algorithm on dev and test sets, adding more data only to the training set doesn't help the algorithm to perform better.


### 15. The City Council thinks that having more Cats in the city would help scare off birds. They are so happy with your work on the Bird detector that they also hire you to build a Cat detector. You have a huge dataset of 100,000,000 cat images. Training on this data takes about two weeks. Which of the statements do you agree with? (Check all that agree.)

- [x] **This significantly impacts iteration speed.**
- [ ] Reducing the model complexity will allow the use of the larger data set but preserve accuracy.
- [x] **Lowering the number of images will reduce training time and likely allow for an acceptable tradeoff between iteration speed and accuracy.**


### 16. The essential difference between an optimizing metric and satisficing metrics is the priority assigned by the stakeholders. True/False?

- [ ] True
- [x] **False**

> 📌 Satisficing metrics have thresholds for measurement and an optimizing metric is unbounded.


### 17. You train a system, and the train/dev set errors are 3.5% and 4.0% respectively. You decide to try regularization to close the train/dev accuracy gap. Do you agree?

- [x] **No, because you do not know what the human performance level is.**
- [ ] ...

> 📌 You need to know what the human performance level is to estimate avoidable bias.


### 18. You ask a few people to label the dataset so as to find out what is human-level performance. You find the following levels of accuracy:

- Bird watching expert #1 - 0.3% error
- Bird watching expert #2 - 0.5% error
- Normal person #1 (not a bird watching expert) - 1.0% error
- Normal person #2 (not a bird watching expert) - 1.2% error

If your goal is to have “human-level performance” be a proxy (or estimate) for Bayes error, how would you define “human-level performance”?

- [x] **0.3% (accuracy of expert #1)**


### 19. Which of the following statements do you agree with?
- [x] **A learning algorithm's performance can be better than human-level performance but it can never be better than Bayes error.**
- [ ] ...


### 20. After running your model with the test set you find it is a 7.0% error compared to a 2.1% error for the dev set and 2.0% for the training set. What can you conclude? (Choose all that apply)
- [x] **You have overfitted to the dev set.** 
- [ ] You should try to get a bigger dev set.
- [ ] Try decreasing regularization for better genenralization with the dev set.
- [ ] You have underfitted to the dev set.


### 21. It turns out Peacetopia has hired one of your competitors to build a system as well. Your system and your competitor both deliver systems with about the same running time and memory size. However, your system has higher accuracy! However, when Peacetopia tries out your and your competitor’s systems, they conclude they actually like your competitor’s system better, because even though you have higher overall accuracy, you have more false negatives (failing to raise an alarm when a bird is in the air). What should you do?

- [x] **Rethink the appropriate metric for this task, and ask your team to tune to the new matric.**
- [ ] Ask your team to take into account both accuracy and false negative rate during development.
- [ ] Look at all the models you've developed during the development process and find the one with the lowest false negative error rate.
- [ ] Pick false negative rate as the new matric, and use this new metric to drive all further development.


### 22. After setting up your train/dev/test sets, the City Council comes across another 1,000,000 images, called the “citizens’ data”. Apparently the citizens of Peacetopia are so scared of birds that they volunteered to take pictures of the sky and label them, thus contributing these additional 1,000,000 images. These images are different from the distribution of images the City Council had originally given you, but you think it could help your algorithm.  <br> <br> Notice that adding this additional data to the training set will make the distribution of the training set different from the distributions of the dev and test sets.   <br> <br> Is the following statement true or false?   <br> <br> "You should not add the citizens' data to the training set, because if the training distribution is different from the dev and test sets, then this will not allow the model to perform well on the test set."

- [ ] True
- [x] **False**

> 📌 Sometimes we'll need to train the model on the data that is available, and its distribution may not be the same as the data that will occur in production. Also, adding training data that differs from the dev set may still help the model improve performance on the dev set. What matters is that the dev and test set have the same distribution.
