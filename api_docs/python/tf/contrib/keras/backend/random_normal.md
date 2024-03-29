<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.random_normal" />
</div>

# tf.contrib.keras.backend.random_normal

``` python
random_normal(
    shape,
    mean=0.0,
    stddev=1.0,
    dtype=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns a tensor with normal distribution of values.

#### Arguments:

    shape: A tuple of integers, the shape of tensor to create.
    mean: A float, mean of the normal distribution to draw samples.
    stddev: A float, standard deviation of the normal distribution
        to draw samples.
    dtype: String, dtype of returned tensor.
    seed: Integer, random seed.


#### Returns:

    A tensor.