<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.count_up_to" />
</div>

# tf.count_up_to

``` python
count_up_to(
    ref,
    limit,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_state_ops.py`.

See the guide: [Control Flow > Control Flow Operations](../../../api_guides/python/control_flow_ops.md#Control_Flow_Operations)

Increments 'ref' until it reaches 'limit'.

#### Args:

* <b>`ref`</b>: A mutable `Tensor`. Must be one of the following types: `int32`, `int64`.
    Should be from a scalar `Variable` node.
* <b>`limit`</b>: An `int`.
    If incrementing ref would bring it above limit, instead generates an
    'OutOfRange' error.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A `Tensor`. Has the same type as `ref`.
  A copy of the input before increment. If nothing else modifies the
  input, the values produced will all be distinct.