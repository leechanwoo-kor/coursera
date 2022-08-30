## Week 4 Quiz - Special Applications

#### 1. Face verification and face recognition are the two most common names given to the task of comparing a new picture against one person's face. True/False?

- [ ] True
- [x] **False**

> 📌 This is the description of face verification, but not of face recognition.

#### 2. Why is the face verification problem considered a one-shot learning problem? Choose the best answer.

- [ ] Because we have only have to forward pass the image one time through our neural network to one specific person.
- [ ] Because we are trying to compare to one specific person only.
- [ ] Because of the sensitive nature of the problem, we won't have a chance to correct it if the network make a mistake.
- [ ] Because we might have only one example of the person we want to verify.

#### 3. You want to build a system that receives a person's face picture and determines if the person is inside a workgroup. You have pictures of all the faces of the people currently in the workgroup, but some members might leave, and some new members might be added. To train a system to solve this problem using the triplet loss you must collect pictures of different faces from only the current members of the team. True/False?

- [ ] True
- [x] **False**

> 📌 Although it is necessary to have several pictures of the same person, it is not absolutely necessary that all the pictures only come from current members of the team.

#### 3-1. You want to build a system that receives a person's face picture and determines if the person is inside a workgroup. You have pictures of all the faces of the people currently in the workgroup, but some members might leave, and some new members might be added. To train a system to solve this problem using the triplet loss you get many persons and take several pictures of each one. Which of the following do you agree with? (Select the best answer.)

- [ ] You take several pictures of the same person because this way you can get more pictures to train the network efficiently since you already have the person in place.
- [ ] It would be best to increase the number of persons in the dataset by taking only one picture of each person to have a more representative set of the population.
- [x] **You take several pictures of the same person to train $d(img_1,img_2)$ using the triplet loss.**
- [ ] You shouldn't use persons outside the workgroup you are interested in because that might create a high variance in your model.

> 📌 To train using the triplet loss you need several pictures of the same person.

#### 4. Which of the following is a correct definition of the triplet loss? Consider that $\alpha > 0$. (We encourage you to figure out the answer from first principles, rather than just refer to the lecture.)

- [x] **$max(||f(A)-f(P)||^2 - ||f(A)-f(N)||^2 + \alpha, 0)$**
- [ ] ...

#### 5. Consider the following Siamese network architecture:

![image](https://user-images.githubusercontent.com/55765292/187367719-055e03d0-8040-4aef-817f-314712c8c4a9.png)

**Which of the following do you agree with the most?

- [ ] The two neural networks depicted in the image have the same architecture, but they might have different parameters.
- [x] The upper and lower neural networks depicted have exactly the same parameters, but the outputs are computed independently for each image.
- [ ] This depicts two different neural networks with different architectures, although we use the same drawing.
- [ ] Although we depict two neural networks and two images, the two images are combined in a single volume and pass through a single neural network.

> 📌 Both neural networks share the same weights, and each image passes through the neural network in an independent manner.

#### 5-1. The upper and lower networks share parameters to have a consistent encoding for both images. True/False?

- [x] **True**
- [ ] False

> 📌 Part of the idea behind the Siamese network is to compare the encoding of the images, thus they must be consistent.

#### 6. You train a ConvNet on a dataset with 100 different classes. You wonder if you can find a hidden unit which responds strongly to pictures of cats. (I.e., a neuron so that, of all the input/training images that strongly activate that neuron, the majority are cat pictures.) You are more likely to find this unit in layer 4 of the network than in layer 1.

- [x] **True**
- [ ] False

> 📌 This neuron understands complex shapes (cat pictures) so it is more likely to be in a deeper layer than in the first layer.

#### 7. Neural style transfer uses images Content C, Style S. The loss function used to generate image G is composed of which of the following: (Choose all that apply.)

- [x] **$J_content$ that compares $C$ and $G$.**
- [x] **J_style$ that compares $S$ and $G$.**
- [ ] ...

#### 8. In neural style transfer the content loss $J_{cont}$ is computed as:

$J_{cont}(G, C) = ||a^{[l] (C)} - a^{[l] (G)}||^2$

**Where $a^{[l] (k)}$ is the activation of the $l$-th layer of a ConvNet trained for classification. We choose $l$ to be a very high value to use compared to the more abstract activation of each image. True/False?**

- [ ] True
- [x] **False**

> 📌 We don't use a very deep layer since this will only compare if the two images belong to the same category.

#### 9. In neural style transfer, which of the following better express the gradients used?

- [ ]

> 📌 We use gradient descent on the cost function J(G).

#### 9-1. In neural style transfer, we can't use gradient descent since there are no trainable parameters. True/False?

- [ ] True
- [x] **False**


> 📌 We use gradient descent on the cost function J(G) and we update the pixel values of the generated image G.

#### 10. You are working with 3D data. You are building a network layer whose input volume has size 32x32x32x16 (this volume has 16 channels), and applies convolutions with 32 filters of dimension 3x3x3x16 (no padding, stride 1). What is the resulting output volume?

- [ ] 30x30x30x16
- [x] **30x30x30x32**
- [ ] Undefined: This convolution step is impossible and cannot be performed because the dimensions specified don't match up.

> 📌 You have used the formula \left\Big\floor n^{[l−1]} − f + 2 \times p / s \right\Big\floor + 1 = n^{[l]}$ over the three first dimensions of the input data.

#### 10-1. You are working with 3D data. The input "image" has size $32 \times 32 \times 32 \times 3$, if you apply a convolutional layer with 16 filters of size $4 \times 4 \times 4$, zero padding and stride 1. What is the size of the output volume?

- [x] **$29 \times 29 \times 29 \times 16$**.
- [ ] 


#### 11. Why do we learn a function $d(img1, img2)d(img1,img2)$ for face verification? (Select all that apply.) 

- [x] **We need to solve a one-shot learning problem.**
- [x] **This allows us to learn to recognize a new person given just a single image of that person.**
- [ ] Given how few images we have per person, we need to apply transfer learning.
- [ ] This allows us to learn to predict a person's identity using a softmax output unit, where the number of classes equals the number of persons in the database plus 1 (for the final "not in database" class).
