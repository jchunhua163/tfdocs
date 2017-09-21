<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.utils.normalize" />
</div>

# tf.contrib.keras.utils.normalize

``` python
normalize(
    x,
    axis=-1,
    order=2
)
```



Defined in [`tensorflow/contrib/keras/python/keras/utils/np_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/utils/np_utils.py).

Normalizes a Numpy array.

#### Arguments:

    x: Numpy array to normalize.
    axis: axis along which to normalize.
    order: Normalization order (e.g. 2 for L2 norm).


#### Returns:

    A normalized copy of the array.