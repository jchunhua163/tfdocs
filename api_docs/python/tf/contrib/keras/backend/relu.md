<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.relu" />
</div>

# tf.contrib.keras.backend.relu

``` python
relu(
    x,
    alpha=0.0,
    max_value=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Rectified linear unit.

With default values, it returns element-wise `max(x, 0)`.

#### Arguments:

    x: A tensor or variable.
    alpha: A scalar, slope of negative section (default=`0.`).
    max_value: Saturation threshold.


#### Returns:

    A tensor.