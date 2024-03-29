<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.random_uniform" />
</div>

# tf.contrib.keras.backend.random_uniform

``` python
random_uniform(
    shape,
    minval=0.0,
    maxval=1.0,
    dtype=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns a tensor with uniform distribution of values.

#### Arguments:

    shape: A tuple of integers, the shape of tensor to create.
    minval: A float, lower boundary of the uniform distribution
        to draw samples.
    maxval: A float, upper boundary of the uniform distribution
        to draw samples.
    dtype: String, dtype of returned tensor.
    seed: Integer, random seed.


#### Returns:

    A tensor.