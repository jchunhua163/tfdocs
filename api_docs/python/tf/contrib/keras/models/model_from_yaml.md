<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.models.model_from_yaml" />
</div>

# tf.contrib.keras.models.model_from_yaml

``` python
model_from_yaml(
    yaml_string,
    custom_objects=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/models.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/models.py).

Parses a yaml model configuration file and returns a model instance.

#### Arguments:

    yaml_string: YAML string encoding a model configuration.
    custom_objects: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

    A Keras model instance (uncompiled).


#### Raises:

    ImportError: if yaml module is not found.