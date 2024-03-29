<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.bitwise.bitwise_and" />
</div>

# tf.bitwise.bitwise_and

``` python
bitwise_and(
    x,
    y,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_bitwise_ops.py`.

Elementwise computes the bitwise AND of `x` and `y`.

The result will have those bits set, that are set in both `x` and `y`. The
computation is performed on the underlying representations of `x` and `y`.

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int8`, `int16`, `int32`, `int64`, `uint8`, `uint16`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A `Tensor`. Has the same type as `x`.