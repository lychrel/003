# MNIST in TensorFlow
using softmax regression
& CNNs

---

### Image Input

put an image being falttened into input vector here

---

### Softmax Implementation

![Softmax](img/s1.png)

![Press Down Key](img/down-arrow.png)

+++

### equation form
![Softmax (equation form)](img/s1_eqns.png)

![Press Down Key](img/down-arrow.png)

+++

### matrix form
![Softmax (matrix form)](img/s1_matrices.png)

![Press Down Key](img/down-arrow.png)

+++

### defining the model 

```python
x = tf.placeholder(tf.float32, [None, 784])
W = tf.Variable(tf.zeros([784, 10]))
b = tf.Variable(tf.zeros([10]))
y = tf.nn.softmax(tf.matmul(x, W) + b)
```

---

## MNIST with SoftMax

![Press Down Key](img/down-arrow.png)

+++?code=mnist_softmax.py&lang=python

@[16-20](tutorial source)
@[21-27](various imports)
@[28-29](load MNIST data)
@[30](load TensorFlow API)
@[32](FLAGS)
@[35-37](import the (one-hot encoded) MNIST data)
@[40-42](create variables, weights, and biases)
@[43](matrix multiplication)
@[46](output layer (predicted probabilities))
@[57-58](define the loss function (measurement of incorrectness))
@[59](define how we want to reduce loss (incorrectness) over time (stochastic gradient descent))
@[61-62](start a session in TensorFlow)
@[64-66](train network using above parameters on 10 sets of 100 images)
@[69-71](check accuracy of predictions)
@[74-79](run session)

---

## Running It
- let's go to the terminal!

---

## Problem

- rotated characters can be hard to recognize

---

## MNIST with CNN

![Press Down Key](img/down-arrow.png)

+++?code=mnist_cnn.py&lang=python

---

# Additional Info

---

## One-Hot Encoding

- one-hot vectors are 0 in all dimensions but one (which is 1).
- avoids assuming order between categories, as integer encoding (1, 2, 3) does.
- e.x. [1,0,0], [0,1,0], [0,0,1] vs 0, 1, 2

---

## SoftMax (normalized exp(x))

- gives a list of values between 0 and 1 that sum to 1
	- a natural choice for probability
- exponentiates inputs then normalizes for pdf
- [more detailed exploration](http://neuralnetworksanddeeplearning.com/chap3.html#softmax)

---

## Cross-Entropy

- measures how inefficient predictions are at describing the truth
- compares predicted probability distribution to true, one-hot encoded probability vector

+++
![Softmax (matrix form)](img/crossent.png)

for predicted distribution _y_, one-hot vector _y'_

---

## Backpropagation

- [detailed introduction](http://colah.github.io/posts/2015-08-Backprop/)

---

## Gradient Descent

- shifting variables small amounts in direction of reduced loss
- [mathy intro](https://en.wikipedia.org/wiki/Gradient_descent)

---

## MNIST Dimensionality

- [detailed exploration](http://colah.github.io/posts/2014-10-Visualizing-MNIST/)

---

## CNN Layers

- convolutional
- ReLu activation
- pooling
- dropout

---

## CNN Hyperparameters

- stride and padding
- filter sizes
- number of (conv) layers

---

## CNN additional detail

- [intro, pt 1](https://adeshpande3.github.io/adeshpande3.github.io/A-Beginner%27s-Guide-To-Understanding-Convolutional-Neural-Networks/)
- [intro, pt 2](https://adeshpande3.github.io/adeshpande3.github.io/A-Beginner's-Guide-To-Understanding-Convolutional-Neural-Networks-Part-2/)
