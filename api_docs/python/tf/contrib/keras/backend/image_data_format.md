<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.image_data_format" />
</div>

# tf.contrib.keras.backend.image_data_format

``` python
image_data_format()
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns the default image data format convention.

#### Returns:

    A string, either `'channels_first'` or `'channels_last'`

Example:
```python
    >>> keras.backend.image_data_format()
    'channels_first'
```