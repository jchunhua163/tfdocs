<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.mean" />
</div>

# tf.contrib.keras.backend.mean

``` python
mean(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Mean of a tensor, alongside the specified axis.

#### Arguments:

    x: A tensor or variable.
    axis: A list of integer. Axes to compute the mean.
    keepdims: A boolean, whether to keep the dimensions or not.
        If `keepdims` is `False`, the rank of the tensor is reduced
        by 1 for each entry in `axis`. If `keep_dims` is `True`,
        the reduced dimensions are retained with length 1.


#### Returns:

    A tensor with the mean of elements of `x`.