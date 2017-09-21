<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.update_sub" />
</div>

# tf.contrib.keras.backend.update_sub

``` python
update_sub(
    x,
    decrement
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Update the value of `x` by subtracting `decrement`.

#### Arguments:

    x: A Variable.
    decrement: A tensor of same shape as `x`.


#### Returns:

    The variable `x` updated.