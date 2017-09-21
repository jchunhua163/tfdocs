<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.optimizers.deserialize" />
</div>

# tf.contrib.keras.optimizers.deserialize

``` python
deserialize(
    config,
    custom_objects=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/optimizers.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/optimizers.py).

Inverse of the `serialize` function.

#### Arguments:

    config: Optimizer configuration dictionary.
    custom_objects: Optional dictionary mapping
        names (strings) to custom objects
        (classes and functions)
        to be considered during deserialization.


#### Returns:

    A Keras Optimizer instance.