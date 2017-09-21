<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.permute_dimensions" />
</div>

# tf.contrib.keras.backend.permute_dimensions

``` python
permute_dimensions(
    x,
    pattern
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Permutes axes in a tensor.

#### Arguments:

    x: Tensor or variable.
    pattern: A tuple of
        dimension indices, e.g. `(0, 2, 1)`.


#### Returns:

    A tensor.