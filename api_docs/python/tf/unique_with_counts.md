<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.unique_with_counts" />
</div>

# tf.unique_with_counts

``` python
unique_with_counts(
    x,
    out_idx=None,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_array_ops.py`.

See the guide: [Tensor Transformations > Slicing and Joining](../../../api_guides/python/array_ops.md#Slicing_and_Joining)

Finds unique elements in a 1-D tensor.

This operation returns a tensor `y` containing all of the unique elements of `x`
sorted in the same order that they occur in `x`. This operation also returns a
tensor `idx` the same size as `x` that contains the index of each value of `x`
in the unique output `y`. Finally, it returns a third tensor `count` that
contains the count of each element of `y` in `x`. In other words:

`y[idx[i]] = x[i] for i in [0, 1,...,rank(x) - 1]`

For example:

```
# tensor 'x' is [1, 1, 2, 4, 4, 4, 7, 8, 8]
y, idx, count = unique_with_counts(x)
y ==> [1, 2, 4, 7, 8]
idx ==> [0, 0, 1, 2, 2, 2, 3, 4, 4]
count ==> [2, 1, 3, 1, 2]
```

#### Args:

* <b>`x`</b>: A `Tensor`. 1-D.
* <b>`out_idx`</b>: An optional `tf.DType` from: `tf.int32, tf.int64`. Defaults to `tf.int32`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A tuple of `Tensor` objects (y, idx, count).

* <b>`y`</b>: A `Tensor`. Has the same type as `x`. 1-D.
* <b>`idx`</b>: A `Tensor` of type `out_idx`. 1-D.
* <b>`count`</b>: A `Tensor` of type `out_idx`. 1-D.