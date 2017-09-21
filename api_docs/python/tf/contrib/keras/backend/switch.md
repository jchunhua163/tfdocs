<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.switch" />
</div>

# tf.contrib.keras.backend.switch

``` python
switch(
    condition,
    then_expression,
    else_expression
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Switches between two operations depending on a scalar value.

Note that both `then_expression` and `else_expression`
should be symbolic tensors of the *same shape*.

#### Arguments:

    condition: scalar tensor (`int` or `bool`).
    then_expression: either a tensor, or a callable that returns a tensor.
    else_expression: either a tensor, or a callable that returns a tensor.


#### Returns:

    The selected tensor.