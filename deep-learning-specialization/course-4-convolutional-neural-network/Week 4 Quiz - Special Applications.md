## Week 4 Quiz - Special Applications

#### 1. Face verification and face recognition are the two most common names given to the task of comparing a new picture against one person's face. True/False?

- [ ] True
- [x] **False**

#### 2. Why is the face verification problem considered a one-shot learning problem? Choose the best answer.

- [ ] Because we have only have to forward pass the image one time through our neural network to one specific person.
- [ ] Because we are trying to compare to one specific person only.
- [ ] Because of the sensitive nature of the problem, we won't have a chance to correct it if the network make a mistake.
- [ ] Because we might have only one example of the person we want to verify.

#### 3. You want to build a system that receives a person's face picture and determines if the person is inside a workgroup. You have pictures of all the faces of the people currently in the workgroup, but some members might leave, and some new members might be added. To train a system to solve this problem using the triplet loss you must collect pictures of different faces from only the current members of the team. True/False?

- [ ] True
- [x] **False**

> 📌 Although it is necessary to have several pictures of the same person, it is not absolutely necessary that all the pictures only come from current members of the team.

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

**Where $a^{[l](k)}$ is the activation of the $l$-th layer of a ConvNet trained for classification. We choose $l$ to be a very high value to use compared to the more abstract activation of each image. True/False?**

- [ ] True
- [x] **False**

#### 9. In neural style transfer, which of the following better express the gradients used?

- [ ]

> 📌 We use gradient descent on the cost function J(G).

#### 10. You are working with 3D data. You are building a network layer whose input volume has size 32x32x32x16 (this volume has 16 channels), and applies convolutions with 32 filters of dimension 3x3x3x16 (no padding, stride 1). What is the resulting output volume?

- [ ] 30x30x30x16
- [x] **30x30x30x32**
- [ ] Undefined: This convolution step is impossible and cannot be performed because the dimensions specified don't match up.

> 📌 You have used the formula \left\Big\floor n^{[l−1]} − f + 2 \times p / s \right\Big\floor + 1 = n^{[l]}$ over the three first dimensions of the input data.
