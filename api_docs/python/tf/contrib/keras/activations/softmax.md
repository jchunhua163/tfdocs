<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.activations.softmax" />
</div>

# tf.contrib.keras.activations.softmax

``` python
softmax(
    x,
    axis=-1
)
```



Defined in [`tensorflow/contrib/keras/python/keras/activations.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/activations.py).

Softmax activation function.

#### Arguments:

    x : Tensor.
    axis: Integer, axis along which the softmax normalization is applied.


#### Returns:

    Tensor, output of softmax transformation.


#### Raises:

    ValueError: In case `dim(x) == 1`.