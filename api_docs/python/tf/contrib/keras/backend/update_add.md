<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.update_add" />
</div>

# tf.contrib.keras.backend.update_add

``` python
update_add(
    x,
    increment
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Update the value of `x` by adding `increment`.

#### Arguments:

    x: A Variable.
    increment: A tensor of same shape as `x`.


#### Returns:

    The variable `x` updated.