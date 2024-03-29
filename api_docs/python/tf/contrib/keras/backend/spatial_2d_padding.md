<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.spatial_2d_padding" />
</div>

# tf.contrib.keras.backend.spatial_2d_padding

``` python
spatial_2d_padding(
    x,
    padding=((1, 1), (1, 1)),
    data_format=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Pads the 2nd and 3rd dimensions of a 4D tensor.

#### Arguments:

    x: Tensor or variable.
    padding: Tuple of 2 tuples, padding pattern.
    data_format: One of `channels_last` or `channels_first`.


#### Returns:

    A padded 4D tensor.


#### Raises:

    ValueError: if `data_format` is neither
        `channels_last` or `channels_first`.