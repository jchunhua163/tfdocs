<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse_reduce_sum_sparse" />
</div>

# tf.sparse_reduce_sum_sparse

``` python
sparse_reduce_sum_sparse(
    sp_input,
    axis=None,
    keep_dims=False,
    reduction_axes=None
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/sparse_ops.py).

See the guide: [Sparse Tensors > Reduction](../../../api_guides/python/sparse_ops.md#Reduction)

Computes the sum of elements across dimensions of a SparseTensor.

This Op takes a SparseTensor and is the sparse counterpart to
`tf.reduce_sum()`.  In contrast to SparseReduceSum, this Op returns a
SparseTensor.

Reduces `sp_input` along the dimensions given in `reduction_axes`.  Unless
`keep_dims` is true, the rank of the tensor is reduced by 1 for each entry in
`reduction_axes`. If `keep_dims` is true, the reduced dimensions are retained
with length 1.

If `reduction_axes` has no entries, all dimensions are reduced, and a tensor
with a single element is returned.  Additionally, the axes can be negative,
which are interpreted according to the indexing rules in Python.

#### Args:

* <b>`sp_input`</b>: The SparseTensor to reduce. Should have numeric type.
* <b>`axis`</b>: The dimensions to reduce; list or scalar. If `None` (the
    default), reduces all dimensions.
* <b>`keep_dims`</b>: If true, retain reduced dimensions with length 1.
* <b>`reduction_axes`</b>: Deprecated name of axis


#### Returns:

  The reduced SparseTensor.