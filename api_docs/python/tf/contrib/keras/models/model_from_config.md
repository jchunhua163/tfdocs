<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.models.model_from_config" />
</div>

# tf.contrib.keras.models.model_from_config

``` python
model_from_config(
    config,
    custom_objects=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/models.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/models.py).

Instantiates a Keras model from its config.

#### Arguments:

    config: Configuration dictionary.
    custom_objects: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

    A Keras model instance (uncompiled).


#### Raises:

    TypeError: if `config` is not a dictionary.