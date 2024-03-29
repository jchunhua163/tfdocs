<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.repeat_elements" />
</div>

# tf.contrib.keras.backend.repeat_elements

``` python
repeat_elements(
    x,
    rep,
    axis
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Repeats the elements of a tensor along an axis, like `np.repeat`.

If `x` has shape `(s1, s2, s3)` and `axis` is `1`, the output
will have shape `(s1, s2 * rep, s3)`.

#### Arguments:

    x: Tensor or variable.
    rep: Python integer, number of times to repeat.
    axis: Axis along which to repeat.


#### Raises:

    ValueError: In case `x.shape[axis]` is undefined.


#### Returns:

    A tensor.