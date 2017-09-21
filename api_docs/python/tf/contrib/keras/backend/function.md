<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.function" />
</div>

# tf.contrib.keras.backend.function

``` python
function(
    inputs,
    outputs,
    updates=None,
    **kwargs
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Instantiates a Keras function.

#### Arguments:

    inputs: List of placeholder tensors.
    outputs: List of output tensors.
    updates: List of update ops.
    **kwargs: Passed to `tf.Session.run`.


#### Returns:

    Output values as Numpy arrays.


#### Raises:

    ValueError: if invalid kwargs are passed in.