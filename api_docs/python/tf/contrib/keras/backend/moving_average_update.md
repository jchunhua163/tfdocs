<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.moving_average_update" />
</div>

# tf.contrib.keras.backend.moving_average_update

``` python
moving_average_update(
    x,
    value,
    momentum
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Compute the moving average of a variable.

#### Arguments:

    x: A Variable.
    value: A tensor with the same shape as `variable`.
    momentum: The moving average momentum.


#### Returns:

    An Operation to update the variable.