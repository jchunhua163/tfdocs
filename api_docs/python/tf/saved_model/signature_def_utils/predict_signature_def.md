<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.signature_def_utils.predict_signature_def" />
</div>

# tf.saved_model.signature_def_utils.predict_signature_def

``` python
predict_signature_def(
    inputs,
    outputs
)
```



Defined in [`tensorflow/python/saved_model/signature_def_utils_impl.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/signature_def_utils_impl.py).

Creates prediction signature from given inputs and outputs.

#### Args:

* <b>`inputs`</b>: dict of string to `Tensor`.
* <b>`outputs`</b>: dict of string to `Tensor`.


#### Returns:

  A prediction-flavored signature_def.


#### Raises:

* <b>`ValueError`</b>: If inputs or outputs is `None`.