<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.map_fn" />
</div>

# tf.contrib.keras.backend.map_fn

``` python
map_fn(
    fn,
    elems,
    name=None,
    dtype=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Map the function fn over the elements elems and return the outputs.

#### Arguments:

    fn: Callable that will be called upon each element in elems
    elems: tensor
    name: A string name for the map node in the graph
    dtype: Output data type.


#### Returns:

    Tensor with dtype `dtype`.