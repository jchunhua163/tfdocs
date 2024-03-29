<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.normalize_batch_in_training" />
</div>

# tf.contrib.keras.backend.normalize_batch_in_training

``` python
normalize_batch_in_training(
    x,
    gamma,
    beta,
    reduction_axes,
    epsilon=0.001
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Computes mean and std for batch then apply batch_normalization on batch.

#### Arguments:

    x: Input tensor or variable.
    gamma: Tensor by which to scale the input.
    beta: Tensor with which to center the input.
    reduction_axes: iterable of integers,
        axes over which to normalize.
    epsilon: Fuzz factor.


#### Returns:

    A tuple length of 3, `(normalized_tensor, mean, variance)`.