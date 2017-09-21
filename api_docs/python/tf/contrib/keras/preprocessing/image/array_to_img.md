<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.preprocessing.image.array_to_img" />
</div>

# tf.contrib.keras.preprocessing.image.array_to_img

``` python
array_to_img(
    x,
    data_format=None,
    scale=True
)
```



Defined in [`tensorflow/contrib/keras/python/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/preprocessing/image.py).

Converts a 3D Numpy array to a PIL Image instance.

#### Arguments:

    x: Input Numpy array.
    data_format: Image data format.
    scale: Whether to rescale image values
        to be within [0, 255].


#### Returns:

    A PIL Image instance.


#### Raises:

    ImportError: if PIL is not available.
    ValueError: if invalid `x` or `data_format` is passed.