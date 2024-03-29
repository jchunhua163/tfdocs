<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.rejection_resample" />
</div>

# tf.contrib.data.rejection_resample

``` python
rejection_resample(
    dataset,
    class_func,
    target_dist,
    initial_dist=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/data/python/ops/dataset_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/dataset_ops.py).

Resamples this dataset to achieve a target class distribution.

**NOTE** Resampling is performed via rejection sampling; some fraction
of the input values will be dropped.

#### Args:

* <b>`dataset`</b>: A `Dataset` object.
* <b>`class_func`</b>: A function mapping a nested structure of tensors (having
    shapes and types defined by `dataset.output_shapes` and
    `dataset.output_types`) to a scalar `tf.int32` tensor.  Values should
    be in `[0, num_classes)`.
* <b>`target_dist`</b>: A floating point type tensor, shaped `[num_classes].
* <b>`initial_dist`</b>: (Optional.)  A floating point type tensor, shaped
    `[num_classes]`.  If not provided, the true class distribution is
    estimated live in a streaming fashion.
* <b>`seed`</b>: (Optional.) Python integer seed for the resampler.


#### Returns:

  A `Dataset`.