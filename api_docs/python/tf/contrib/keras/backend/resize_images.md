<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.resize_images" />
</div>

# tf.contrib.keras.backend.resize_images

``` python
resize_images(
    x,
    height_factor,
    width_factor,
    data_format
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Resizes the images contained in a 4D tensor.

#### Arguments:

    x: Tensor or variable to resize.
    height_factor: Positive integer.
    width_factor: Positive integer.
    data_format: One of `"channels_first"`, `"channels_last"`.


#### Returns:

    A tensor.


#### Raises:

    ValueError: if `data_format` is neither
        `channels_last` or `channels_first`.