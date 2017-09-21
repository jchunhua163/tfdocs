<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.foldl" />
</div>

# tf.contrib.keras.backend.foldl

``` python
foldl(
    fn,
    elems,
    initializer=None,
    name=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Reduce elems using fn to combine them from left to right.

#### Arguments:

    fn: Callable that will be called upon each element in elems and an
        accumulator, for instance `lambda acc, x: acc + x`
    elems: tensor
    initializer: The first value used (`elems[0]` in case of None)
    name: A string name for the foldl node in the graph


#### Returns:

    Tensor with same type and shape as `initializer`.