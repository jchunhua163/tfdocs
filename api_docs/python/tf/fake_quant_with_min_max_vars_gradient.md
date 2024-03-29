<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.fake_quant_with_min_max_vars_gradient" />
</div>

# tf.fake_quant_with_min_max_vars_gradient

``` python
fake_quant_with_min_max_vars_gradient(
    gradients,
    inputs,
    min,
    max,
    num_bits=None,
    narrow_range=None,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_array_ops.py`.

See the guide: [Tensor Transformations > Fake quantization](../../../api_guides/python/array_ops.md#Fake_quantization)

Compute gradients for a FakeQuantWithMinMaxVars operation.

#### Args:

* <b>`gradients`</b>: A `Tensor` of type `float32`.
    Backpropagated gradients above the FakeQuantWithMinMaxVars operation.
* <b>`inputs`</b>: A `Tensor` of type `float32`.
    Values passed as inputs to the FakeQuantWithMinMaxVars operation.
    min, max: Quantization interval, scalar floats.
* <b>`min`</b>: A `Tensor` of type `float32`.
* <b>`max`</b>: A `Tensor` of type `float32`.
* <b>`num_bits`</b>: An optional `int`. Defaults to `8`.
    The bitwidth of the quantization; between 2 and 8, inclusive.
* <b>`narrow_range`</b>: An optional `bool`. Defaults to `False`.
    Whether to quantize into 2^num_bits - 1 distinct values.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A tuple of `Tensor` objects (backprops_wrt_input, backprop_wrt_min, backprop_wrt_max).

* <b>`backprops_wrt_input`</b>: A `Tensor` of type `float32`. Backpropagated gradients w.r.t. inputs:
    `gradients * (inputs >= min && inputs <= max)`.
* <b>`backprop_wrt_min`</b>: A `Tensor` of type `float32`. Backpropagated gradients w.r.t. min parameter:
    `sum(gradients * (inputs < min))`.
* <b>`backprop_wrt_max`</b>: A `Tensor` of type `float32`. Backpropagated gradients w.r.t. max parameter:
    `sum(gradients * (inputs > max))`.