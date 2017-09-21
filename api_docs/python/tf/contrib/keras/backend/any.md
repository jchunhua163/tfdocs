<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.any" />
</div>

# tf.contrib.keras.backend.any

``` python
any(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Bitwise reduction (logical OR).

#### Arguments:

    x: Tensor or variable.
    axis: axis along which to perform the reduction.
    keepdims: whether the drop or broadcast the reduction axes.


#### Returns:

    A uint8 tensor (0s and 1s).