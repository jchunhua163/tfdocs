<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.batch_normalization" />
</div>

# tf.contrib.keras.backend.batch_normalization

``` python
batch_normalization(
    x,
    mean,
    var,
    beta,
    gamma,
    epsilon=0.001
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Applies batch normalization on x given mean, var, beta and gamma.

I.e. returns:
`output = (x - mean) / (sqrt(var) + epsilon) * gamma + beta`

#### Arguments:

    x: Input tensor or variable.
    mean: Mean of batch.
    var: Variance of batch.
    beta: Tensor with which to center the input.
    gamma: Tensor by which to scale the input.
    epsilon: Fuzz factor.


#### Returns:

    A tensor.