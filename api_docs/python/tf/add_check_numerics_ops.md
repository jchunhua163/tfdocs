<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.add_check_numerics_ops" />
</div>

# tf.add_check_numerics_ops

``` python
add_check_numerics_ops()
```



Defined in [`tensorflow/python/ops/numerics.py`](https://www.tensorflow.org/code/tensorflow/python/ops/numerics.py).

See the guide: [Control Flow > Debugging Operations](../../../api_guides/python/control_flow_ops.md#Debugging_Operations)

Connect a `check_numerics` to every floating point tensor.

`check_numerics` operations themselves are added for each `half`, `float`,
or `double` tensor in the graph. For all ops in the graph, the
`check_numerics` op for all of its (`half`, `float`, or `double`) inputs
is guaranteed to run before the `check_numerics` op on any of its outputs.

#### Returns:

  A `group` op depending on all `check_numerics` ops added.