<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.squeeze" />
</div>

# tf.contrib.keras.backend.squeeze

``` python
squeeze(
    x,
    axis
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Removes a 1-dimension from the tensor at index "axis".

#### Arguments:

    x: A tensor or variable.
    axis: Axis to drop.


#### Returns:

    A tensor with the same data as `x` but reduced dimensions.