<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.stop_gradient" />
</div>

# tf.contrib.keras.backend.stop_gradient

``` python
stop_gradient(variables)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Returns `variables` but with zero gradient w.r.t. every other variable.

#### Arguments:

    variables: List of variables.


#### Returns:

    The same list of variables.