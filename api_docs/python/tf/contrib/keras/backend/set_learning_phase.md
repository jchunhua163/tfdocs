<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.set_learning_phase" />
</div>

# tf.contrib.keras.backend.set_learning_phase

``` python
set_learning_phase(value)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Sets the learning phase to a fixed value.

#### Arguments:

    value: Learning phase value, either 0 or 1 (integers).


#### Raises:

    ValueError: if `value` is neither `0` nor `1`.