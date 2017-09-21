<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.stack" />
</div>

# tf.contrib.keras.backend.stack

``` python
stack(
    x,
    axis=0
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Stacks a list of rank `R` tensors into a rank `R+1` tensor.

#### Arguments:

    x: List of tensors.
    axis: Axis along which to perform stacking.


#### Returns:

    A tensor.