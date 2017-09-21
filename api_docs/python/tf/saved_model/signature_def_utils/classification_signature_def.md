<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.signature_def_utils.classification_signature_def" />
</div>

# tf.saved_model.signature_def_utils.classification_signature_def

``` python
classification_signature_def(
    examples,
    classes,
    scores
)
```



Defined in [`tensorflow/python/saved_model/signature_def_utils_impl.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/signature_def_utils_impl.py).

Creates classification signature from given examples and predictions.

#### Args:

* <b>`examples`</b>: `Tensor`.
* <b>`classes`</b>: `Tensor`.
* <b>`scores`</b>: `Tensor`.


#### Returns:

  A classification-flavored signature_def.


#### Raises:

* <b>`ValueError`</b>: If examples is `None`.