<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse_segment_mean" />
</div>

# tf.sparse_segment_mean

``` python
sparse_segment_mean(
    data,
    indices,
    segment_ids,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Segmentation](../../../api_guides/python/math_ops.md#Segmentation)

Computes the mean along sparse segments of a tensor.

Read [the section on segmentation](../../../api_guides/python/math_ops.md#segmentation) for an explanation of
segments.

Like `SegmentMean`, but `segment_ids` can have rank less than `data`'s first
dimension, selecting a subset of dimension 0, specified by `indices`.

#### Args:

* <b>`data`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`indices`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    A 1-D tensor. Has same rank as `segment_ids`.
* <b>`segment_ids`</b>: A `Tensor` of type `int32`.
    A 1-D tensor. Values should be sorted and can be repeated.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A `Tensor`. Has the same type as `data`.
  Has same shape as data, except for dimension 0 which
  has size `k`, the number of segments.