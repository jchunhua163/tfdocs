<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.set_epsilon" />
</div>

# tf.contrib.keras.backend.set_epsilon

``` python
set_epsilon(value)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Sets the value of the fuzz factor used in numeric expressions.

#### Arguments:

    value: float. New value of epsilon.

Example:
```python
    >>> from keras import backend as K
    >>> K.epsilon()
    1e-08
    >>> K.set_epsilon(1e-05)
    >>> K.epsilon()
    1e-05
```