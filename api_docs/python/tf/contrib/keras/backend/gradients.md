<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.gradients" />
</div>

# tf.contrib.keras.backend.gradients

``` python
gradients(
    loss,
    variables
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns the gradients of `variables` w.r.t. `loss`.

#### Arguments:

    loss: Scalar tensor to minimize.
    variables: List of variables.


#### Returns:

    A gradients tensor.