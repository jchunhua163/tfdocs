<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.stack" />
</div>

# tf.stack

``` python
stack(
    values,
    axis=0,
    name='stack'
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

See the guides: [Layers (contrib) > Higher level ops for building neural network layers](../../../api_guides/python/contrib.layers.md#Higher_level_ops_for_building_neural_network_layers), [Tensor Transformations > Slicing and Joining](../../../api_guides/python/array_ops.md#Slicing_and_Joining)

Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor.

Packs the list of tensors in `values` into a tensor with rank one higher than
each tensor in `values`, by packing them along the `axis` dimension.
Given a list of length `N` of tensors of shape `(A, B, C)`;

if `axis == 0` then the `output` tensor will have the shape `(N, A, B, C)`.
if `axis == 1` then the `output` tensor will have the shape `(A, N, B, C)`.
Etc.

For example:

```python
# 'x' is [1, 4]
# 'y' is [2, 5]
# 'z' is [3, 6]
stack([x, y, z])  # => [[1, 4], [2, 5], [3, 6]] (Pack along first dim.)
stack([x, y, z], axis=1)  # => [[1, 2, 3], [4, 5, 6]]
```

This is the opposite of unstack.  The numpy equivalent is

```python
tf.stack([x, y, z]) = np.asarray([x, y, z])
```

#### Args:

* <b>`values`</b>: A list of `Tensor` objects with the same shape and type.
* <b>`axis`</b>: An `int`. The axis to stack along. Defaults to the first dimension.
    Supports negative indexes.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

* <b>`output`</b>: A stacked `Tensor` with the same type as `values`.


#### Raises:

* <b>`ValueError`</b>: If `axis` is out of the range [-(R+1), R+1).