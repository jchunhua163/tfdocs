<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.preprocessing.image.img_to_array" />
</div>

# tf.contrib.keras.preprocessing.image.img_to_array

``` python
img_to_array(
    img,
    data_format=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/preprocessing/image.py).

Converts a PIL Image instance to a Numpy array.

#### Arguments:

    img: PIL Image instance.
    data_format: Image data format.


#### Returns:

    A 3D Numpy array.


#### Raises:

    ValueError: if invalid `img` or `data_format` is passed.