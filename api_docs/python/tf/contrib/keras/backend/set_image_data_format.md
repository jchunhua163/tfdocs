<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.set_image_data_format" />
</div>

# tf.contrib.keras.backend.set_image_data_format

``` python
set_image_data_format(data_format)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Sets the value of the image data format convention.

#### Arguments:

    data_format: string. `'channels_first'` or `'channels_last'`.

Example:
```python
    >>> from keras import backend as K
    >>> K.image_data_format()
    'channels_first'
    >>> K.set_image_data_format('channels_last')
    >>> K.image_data_format()
    'channels_last'
```


#### Raises:

    ValueError: In case of invalid `data_format` value.