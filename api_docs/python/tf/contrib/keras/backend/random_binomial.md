<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.random_binomial" />
</div>

# tf.contrib.keras.backend.random_binomial

``` python
random_binomial(
    shape,
    p=0.0,
    dtype=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns a tensor with random binomial distribution of values.

#### Arguments:

    shape: A tuple of integers, the shape of tensor to create.
    p: A float, `0. <= p <= 1`, probability of binomial distribution.
    dtype: String, dtype of returned tensor.
    seed: Integer, random seed.


#### Returns:

    A tensor.