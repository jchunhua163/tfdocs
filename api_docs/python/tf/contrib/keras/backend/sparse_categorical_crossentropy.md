<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.sparse_categorical_crossentropy" />
</div>

# tf.contrib.keras.backend.sparse_categorical_crossentropy

``` python
sparse_categorical_crossentropy(
    output,
    target,
    from_logits=False
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Categorical crossentropy with integer targets.

#### Arguments:

    output: A tensor resulting from a softmax
        (unless `from_logits` is True, in which
        case `output` is expected to be the logits).
    target: An integer tensor.
    from_logits: Boolean, whether `output` is the
        result of a softmax, or is a tensor of logits.


#### Returns:

    Output tensor.