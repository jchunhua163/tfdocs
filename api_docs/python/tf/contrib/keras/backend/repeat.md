<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.repeat" />
</div>

# tf.contrib.keras.backend.repeat

``` python
repeat(
    x,
    n
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Repeats a 2D tensor.

if `x` has shape (samples, dim) and `n` is `2`,
the output will have shape `(samples, 2, dim)`.

#### Arguments:

    x: Tensor or variable.
    n: Python integer, number of times to repeat.


#### Returns:

    A tensor.