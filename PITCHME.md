# MNIST with Softmax Regressions
Simpler classification method

---

### MNIST Softmax in TensorFlow

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

### in code

```python
x = tf.placeholder(tf.float32, [None, 784])
W = tf.Variable(tf.zeros([784, 10]))
b = tf.Variable(tf.zeros([10]))
y = tf.nn.softmax(tf.matmul(x, W) + b)
```

---

## Full Code

+++?code=mnist_softmax.py&lang=python

@[16-20](tutorial source)
@[21-27](various imports)
@[28-29](load the MNIST data)
@[30](load TensorFlow API)
@[32](FLAGS)
@[35-37](import the MNIST data)
@[40-42](create variable, weights, and biases)
@[43](matrix multiplication)
@[46](it gets complicated lol)

---