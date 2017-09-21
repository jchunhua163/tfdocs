<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.is_gpu_available" />
</div>

# tf.test.is_gpu_available

``` python
is_gpu_available(cuda_only=False)
```



Defined in [`tensorflow/python/platform/test.py`](https://www.tensorflow.org/code/tensorflow/python/platform/test.py).

See the guide: [Testing > Utilities](../../../../api_guides/python/test.md#Utilities)

Returns whether TensorFlow can access a GPU.

#### Args:

* <b>`cuda_only`</b>: limit the search to CUDA gpus.


#### Returns:

  True iff a gpu device of the requested kind is available.