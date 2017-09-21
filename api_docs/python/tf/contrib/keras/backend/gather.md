<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.gather" />
</div>

# tf.contrib.keras.backend.gather

``` python
gather(
    reference,
    indices
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Retrieves the elements of indices `indices` in the tensor `reference`.

#### Arguments:

    reference: A tensor.
    indices: An integer tensor of indices.


#### Returns:

    A tensor of same type as `reference`.