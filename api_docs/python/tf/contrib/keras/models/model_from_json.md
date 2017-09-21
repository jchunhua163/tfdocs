<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.models.model_from_json" />
</div>

# tf.contrib.keras.models.model_from_json

``` python
model_from_json(
    json_string,
    custom_objects=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/models.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/models.py).

Parses a JSON model configuration file and returns a model instance.

#### Arguments:

    json_string: JSON string encoding a model configuration.
    custom_objects: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

    A Keras model instance (uncompiled).