<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.one_hot" />
</div>

# tf.contrib.keras.backend.one_hot

``` python
one_hot(
    indices,
    num_classes
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Computes the one-hot representation of an integer tensor.

#### Arguments:

    indices: nD integer tensor of shape
        `(batch_size, dim1, dim2, ... dim(n-1))`
    num_classes: Integer, number of classes to consider.


#### Returns:

    (n + 1)D one hot representation of the input
    with shape `(batch_size, dim1, dim2, ... dim(n-1), num_classes)`


#### Returns:

    The one-hot tensor.