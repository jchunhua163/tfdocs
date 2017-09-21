<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.dropout" />
</div>

# tf.contrib.keras.backend.dropout

``` python
dropout(
    x,
    level,
    noise_shape=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Sets entries in `x` to zero at random, while scaling the entire tensor.

#### Arguments:

    x: tensor
    level: fraction of the entries in the tensor
        that will be set to 0.
    noise_shape: shape for randomly generated keep/drop flags,
        must be broadcastable to the shape of `x`
    seed: random seed to ensure determinism.


#### Returns:

    A tensor.