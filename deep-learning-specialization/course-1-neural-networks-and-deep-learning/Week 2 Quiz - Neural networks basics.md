## Week 1 Quiz - Introduction to deep learning


### 1. What does a neuron compute?
- [ ] A neuron computes a linear function $z = Wx + b$ followed by an activation function.
- [ ] A neuron computes the mean of all features before applying the output to an activation function.
- [x] **A neuron computes an activation function followed by a linear function z = Wx + b.**
- [ ] A neuron computes a function g that scales the input x linearly (Wx + b)
```
📌 We generally say that the output of a neuron is a = g(Wx + b) where g is the activation function (sigmoid, tanh, ReLU, ...).
```


### 2. Which of thes is the "Logistic Loss"?
- [x] **L^{(i)}(\hat{y}^{(i)},y^{(i)})=-(y^{(i)}\log{\hat{y}^{(i)}})+(1-y^{(i))\log{1-\hat{y}^{(i)})**
- [ ] ...

📌 $L^{(i)}(\hat{y}^{(i)},y^{(i)})=-(y^{(i)} \log{ \hat{y}^{(i)} }) + (1-y^{(i)})\log{(1-\hat{y}^{(i)})})$


### 3. Consider the Numpy array x:
```
x = np.array([[[1],[2]],[[3],[4]]])
```
**What is the shape of x?**
- [ ] (4, )
- [ ] (1, 2, 2)
- [x] **(2, 2, 1)**
- [ ] (2, 2)


### 4. Consider the following random arrays a and b, and c:
```
a = np.random.randn(3,3) # a.shape = (3,3)
b = np.random.randn(2,1) # b.shape = (2,1)
c = a + b
```
**What will be the shape of $c$?**
- [x] **The computation cannot happen because it is not possible to bradcast more than one dimension**
- [ ] c.shape = (3,3)
- [ ] c.shape = (2,1)
- [ ] c.shape = (2,3,3)
```
📌 It is not possible to broadcast together a and b. In this case there is no way to generate copies of one of the arrays to match the size of the other.
```


### 5. Consider the two following random arrays a and b:
```
a = np.random.randn(1,3) # a.shape = (1,3)
b = np.random.randn(3,3) # b.shape = (3,3)
c = a * b
```
**What will be the shape of $c$?**
- [x] **c.shape = (3,3)**
- [ ] The computation cannot happen because the sizes don't match.
- [ ] c.shape = (1,3)
- [ ] The computation cannot happen because it is not possible to broadcast more than one dimension.
```
📌 Broadcasting allows row a to be multiplied element-wise with each row of b to from c.
```


### 6. Suppose you have n_x, input features per example. If we decide to use row vector x_j, for the features and X = $\begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_m \\ \end{bmatrix}$ What is the dimension of X?
- [ ] (1,n_x)
- [x] **(m,n_x)**
- [ ] (n_x,n_x)
- [ ] (n_x,m)
📌 Each $x_j$ has dimension $1 \times n_x$, $X$ is built stacking all rows together into a $m \times n_x$ array.


### 7. Recall that np.dot(a,b) performs a matrix multiplication on a and b, whereas a * b performs an element-wise multiplication. Consider two following random arrays a and b:
```
a = np.random.randn(12288, 150) # a.shape(12288, 150)
b = np.random.randn(150, 45) # b.shape(150, 45)
c = np.dot(a, b)
```
**What is the shape of c?**
- [ ] c.shape = (112288, 150)
- [ ] The computation cannot happen because the sizes don't match. It's going to be "Error"!
- [ ] c.shape = (150, 150)
- [x] **c.shape = (12288,45)**
```
📌 Remember that a np.dot(a, b) has shape (number of rows of a, number of columns of b). The sizes match because:  "number of columns of a = 150 = number of rows of b"
```


### 8. Consider the following code snippet:
```
a.shape = (3,4)
b.shape = (4,1)
```
```
for i in range(3):
    for j in range(4):
        c[i][j] = a[i][j]*b[j]
```
**How do you vectorize this?**
- [ ] c = a*b
- [ ] c = np.dot(a,b)
- [ ] c = a.T*b
- [x] **c = a*b.T**
```
📌 b.T gives a column vector with shape (1, 4). The result of c is equivalent to broadcasting a*b.T.
```


### 9. Consider the following code:
```
a = np.random.randn(3,3)
b = np.random.randn(3,1)
c = a*b
```
**What will be c? (If you're not sure, feel free to run this in python to find out).**
- [ ] This will be multiply a 3x3 matrix a with a 3x1 vector, thus resulting in a 3x1 vector. That is, c.shape = (3,1).
- [ ] It will lead to an error since you cannot use "*" to operate on these two matrices. You need to instead use np.dot(a,b)
- [x] **This will invoke broadcasting, so b is copied three times to become (3,3), and * is an element-wise product so c.shape will be (3,3)**
- [ ] This will invoke broadcasting, so b is copied three times to become(3,3), and * invokes a matrix multiplication operation of two 3x3 matrices so c.shape will be (3,3)


### 10. Consider the following computational graph.

![image](https://user-images.githubusercontent.com/55765292/174533750-d174feff-815d-47c8-92b8-73d97add1f18.png)

**What is the output of J?**
- [x] **a^2 - b^2**
- [ ] ...

📌 $J=r+s=u \times v+w \times x=(a+b) \times (a-b)+(b+c) \times (b-c)=a^2-b^2+b^2-c^2=a^2-c^2$
