<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sigmoid" />
</div>

# tf.sigmoid

### Aliases:

* `tf.nn.sigmoid`
* `tf.sigmoid`

``` python
sigmoid(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Neural Network > Activation Functions](../../../api_guides/python/nn.md#Activation_Functions)

Computes sigmoid of `x` element-wise.

Specifically, `y = 1 / (1 + exp(-x))`.

#### Args:

* <b>`x`</b>: A Tensor with type `float32`, `float64`, `int32`, `complex64`, `int64`,
    or `qint32`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A Tensor with the same type as `x` if `x.dtype != qint32`
    otherwise the return type is `quint8`.



#### numpy compatibility
Equivalent to np.scipy.special.expit

