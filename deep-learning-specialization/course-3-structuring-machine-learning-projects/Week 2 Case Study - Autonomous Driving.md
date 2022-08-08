## Week 2 Case Study - Autonomous Driving


### quiz 1.
**To help you practice strategies for machine learning, this week we’ll present another scenario and ask how you would act. We think this “simulator” of working in a machine learning project will give an idea of what leading a machine learning project could be like!**

**You are employed by a startup building self-driving cars. You are in charge of detecting road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. As an example, this image contains a pedestrian crossing sign and red traffic lights.**

![image](https://user-images.githubusercontent.com/55765292/183345637-9e76db9d-f861-4814-92c5-136352ba91cb.png)

**Your 100,000 labeled images are taken using the front-facing camera of your car. This is also the distribution of data you care most about doing well on. You think you might be able to get a much larger dataset off the internet, which could be helpful for training even if the distribution of internet data is not the same.**

**You are getting started with this project. What is the first thing you do? Assume each of the steps below would take about an equal amount of time (a few days).**

- [ ] Invest a few days in thinking on potential difficulties, and then some more days brainstorming about possible solutions, before training any model.
- [ ] Spend a few days, collecting more data using the front-facing camera of your car, to better understand how much data per unit time you can collect.
- [ ] Spend some time searching the internet for the data most similar to the conditions you expect on production.
- [x] **Train a basic model and do error analysis.**

> 📌 Applied ML is highly iterative. Having a basic model to do an error analysis can point you in the most promising directions with a lot of certainties.


### 2. Your goal is to detect road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. You plan to use a deep neural network with ReLU units in the hidden layers.  For the output layer, a softmax activation would be a good choice for the output layer because this is a multi-task learning problem. True/False?

- [ ] True
- [x] **False**

> 📌 Softmax would be a good choice if one and only one of the possibilities (stop sign, speed bump, pedestrian crossing, green light and red light) was present in each image.


### 3. You are working out error analysis and counting up what errors the algorithm makes. Which of the following do you think you should manually go through and carefully examine, one image at a time?

- [x] 500 images on which the algorithm mada a mistake
- [ ] ...

> 📌 Focus on images that the algorithm got wrong. Also, 500 is enough to give you a good initial sense of the error statistics. There’s probably no need to look at 10,000, which will take a long time.


### 4. After working on the data for several weeks, your team ends up with the following data: 

![image](https://user-images.githubusercontent.com/55765292/183347161-a0dace3c-042f-4cc9-b9e5-00ed9ac6c5ca.png)

- [ ] True
- [x] **False**

> 📌 As seen in the lecture on multi-task learning, you can compute the cost such that it is not influenced by the fact that some entries haven’t been labeled.



### 5. The distribution of data you care about contains images from your car’s front-facing camera, which comes from a different distribution than the images you were able to find and download off the internet. Which of the following are true about the train/dev/test split?

- [x] **The dev and test set must come from the front-facing camera.**
- [ ] The train, dev, and test must come from the same distribution.
- [ ] The dev and test sets must contain some images from the internet.
- [ ] The dev and test sets must come from the same distribution.

### 5-1. The distribution of data you care about contains images from your car’s front-facing camera, which comes from a different distribution than the images you were able to find and download off the internet. The best way to split the data is using the 900,000 internet images to train, and divide the 100,000 images from your car's front-facing camera between dev and test sets. True/False?

- [x] **False**
- [ ] True

> 📌 100,000 images are too many to use in dev and test. A better distribution would be to use 80,000 of those images to train, and split the rest between dev and test.


### 6. Assume you’ve finally chosen the following split between the data:

![image](https://user-images.githubusercontent.com/55765292/183347450-25464a84-785d-482e-921e-19c6e4901771.png)

- [ ] You have a too low avoidable bias.
- [x] **You have a high bias.**
- [ ] You have a high variance problem.
- [ ] YOu have a large data-mismatch problem.

> 📌 The avoidable bias is significantly high since the training error is a lot higher than the human-level error.


### 7. Assume you’ve finally chosen the following split between the data:

![image](https://user-images.githubusercontent.com/55765292/183348415-40d943ec-5674-468e-ad3a-1fad1c348e0d.png)

- [ ] True
- [x] **False**


### 8. You decide to focus on the dev set and check by hand what the errors are due to. Here is a table summarizing your discoveries: 

![image](https://user-images.githubusercontent.com/55765292/183348529-a03e8009-0f63-4f55-92ba-bd36e2388f42.png)

> 📌 These kinds of arguments don't help us to decide on the strategy to follow. Other factors should be used, such as the tradeoff between the cost of getting new images and the improvement of the system performance.


### 9. You can buy a specially designed windshield wiper that helps wipe off some of the raindrops on the front-facing camera. 

![image](https://user-images.githubusercontent.com/55765292/183348725-a6498f3f-3980-4152-961e-b7b9e9ec1f3c.png)

- [x] **2.2% would be a reasonable estimate of the maximum amount this windshield wiper could improve performance.**
- [ ] 2.2% would be a reasonable estimate of the minimum amount this windshield wiper could improve performance.
- [ ] 2.2% would be a reasonable estimate of how much this windshield wiper could worsen performance in the worst case.
- [ ] 2.2% would be a reasonable estimate of how much this windshield wiper will improve performance.

> 📌 You will probably not improve performance by more than 2.2% by solving the raindrops problem. If your dataset was infinitely big, 2.2% would be a perfect estimate of the improvement you can achieve by purchasing a specially designed windshield wiper that removes the raindrops.


### 10. You decide to use data augmentation to address foggy images. You find 1,000 pictures of fog off the internet, and “add” them to clean images to synthesize foggy days, like this:

![image](https://user-images.githubusercontent.com/55765292/183349061-717292d0-0785-4617-8a78-00f49878afef.png)

**Which of the following do you agree with?**

- [ ] If used, the synthetic data should be added to the training set.
- [ ] With this technique, we duplicate the size of the training set by synthesizing a new foggy image for each image in the training set.
- [ ] It is irrelvant how the resulting foggy images are perceived by the human eye, the most important thing is that they are correctly synthesized.
- [ ] If used, the synthetic data should be added to the training/dev/test sets in equal proportions.

> 📌 The cost of searching for that many fog images might not be worth the improvement. Also, there is a risk of overfitting to the subset of the foggy image.

### 10-1. We can't use this data since they have a different distribution from the ones we used (internet and front-facing camera). True/False?

- [ ] True
- [x] **False**

> 📌 The new synthesized images are added to the training set and as long as they look realistic to the human eye this will be useful data to train the model.


### 11. After working further on the problem, you've decided to correct the incorrectly labeled data. Your team corrects the labels of the wrongly predicted images on the dev set. Which of the following is a necessary step to take?

- [ ] Use a correctly labeled version and an incorrectly labeled version to make the model more robust.
- [x] **Correct the labels of the test set.**
- [ ] Correct the labels of the train set.
- [ ] Create a train-dev set to estimate how many incorrectly labeled examples are in the train set.

> 📌 Recall that the dev set and the test set must come from the same distribution.


### 12. So far your algorithm only recognizes red and green traffic lights. One of your colleagues in the startup is starting to work on recognizing a yellow traffic light. (Some countries call it an orange light rather than a yellow light; we’ll use the US convention of calling it yellow.) Images containing yellow lights are quite rare, and she doesn’t have enough data to build a good model. She hopes you can help her out using transfer learning.  <br/><br/>What do you tell your colleague?

- [ ] Recommend that she try multe-task learning instead of transfer learning using all the data.
- [x] **She should try using weights pre-trained on your dataset, and fine-tuning further with the yellow-light dataset.**
- [ ] If she has (say) 10,000 images of yellow lights, randomly sample 10,000 images from your dataset and put your and her data together. This prevents your dataset from "swamping" the yellow lights dataset.
- [ ] You cannot help her because the distribution of data you have is different from hers, and is also lacking the yellow label.

> 📌 You have trained your model on a huge dataset, and she has a small dataset. Although your labels are different, the parameters of your model have been trained to recognize many characteristics of road and traffic images which will be useful for her problem. This is a perfect case for transfer learning, she can start with a model with the same architecture as yours, change what is after the last hidden layer and initialize it with your trained parameters.

### 12-1. Your client asks you to add the capability to detect dogs that may be crossing the road to the system. He can provide a relatively small set containing dogs. Which of the following do you agree most with?

- [x] You can use weight pre-trained on the original data, and fine-tune with the data now including the dogs.
- [ ] ...

> 📌 Since your model has learned useful low-level features to tackle the new task we can conserve those by using the pre-trained weights.


### 13. One of your colleagues at the startup is starting a project to classify stop signs in the road as speed limit signs or not. He has approximately 30,000 examples of each image and 30,000 images without a sign. He thought of using your model and applying transfer learning but then he noticed that you use multi-task learning, hence he can't use your model. True/False?

- [ ] True
- [x] **False**

> 📌 When using transfer learning we can remove the last layer. That is one of the aspects that is different from a binary classification problem.

### 13-1. One of your colleagues at the startup is starting a project to classify road signs as stop, dangerous curve, construction ahead, dead-end, and speed limit signs. He has approximately 30,000 examples of each image and 30,000 images without a sign. This case could benefit from using multi-task learning. True/False?

- [x] **True**
- [ ] False

> 📌 There are a lot of high-level features that all the required signs share. This is a great scenario to make use of multi-task learning.


### 14. To recognize red and green lights, you have been using this approach:

- **(A) Input an image (x) to a neural network and have it directly learn a mapping to make a prediction as to whether there’s a red light and/or green light (y).**

**A teammate proposes a different, two-step approach:**

- **(B) In this two-step approach, you would first (i) detect the traffic light in the image (if any), then (ii) determine the color of the illuminated lamp in the traffic light.**

**Between these two, Approach B is more of an end-to-end approach because it has distinct steps for the input end and the output end. True/False?**

- [ ] True
- [x] **False**

> 📌 (A) is an end-to-end approach as it maps directly the input (x) to the output (y).


### 15. To recognize red and green lights, you have been using this approach:

- **(A) Input an image (x) to a neural network and have it directly learn a mapping to make a prediction as to whether there’s a red light and/or green light (y).**

- **(B) In this two-step approach, you would first (i) detect the traffic light in the image (if any), then (ii) determine the color of the illuminated lamp in the traffic light.**

**Approach A tends to be more promising than approach B if you have a ________ (fill in the blank).**

- [ ] Multi-task learning problem.
- [x] **Large training set**
- [ ] Problem with a high Bayes error.
- [ ] Large bias problem.

> 📌 In many fields, it has been observed that end-to-end learning works better in practice, but requires a large amount of data.


### 16. An end-to-end approach doesn't require that we hand-design useful features, it only requires a large enough model. True/False?

- [x] **True**
- [ ] False

> 📌 This is one of the major characteristics of deep learning models, that we don't need to hand-design the features.
