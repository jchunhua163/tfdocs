<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.transpose" />
</div>

# tf.contrib.keras.backend.transpose

``` python
transpose(x)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Transposes a tensor and returns it.

#### Arguments:

    x: Tensor or variable.


#### Returns:

    A tensor.

Examples:
```python
    >>> var = K.variable([[1, 2, 3], [4, 5, 6]])
    >>> K.eval(var)
    array([[ 1.,  2.,  3.],
           [ 4.,  5.,  6.]], dtype=float32)
    >>> var_transposed = K.transpose(var)
    >>> K.eval(var_transposed)
    array([[ 1.,  4.],
           [ 2.,  5.],
           [ 3.,  6.]], dtype=float32)
```

```python
    >>> input = K.placeholder((2, 3))
    >>> input
    <tf.Tensor 'Placeholder_11:0' shape=(2, 3) dtype=float32>
    >>> input_transposed = K.transpose(input)
    >>> input_transposed
    <tf.Tensor 'transpose_4:0' shape=(3, 2) dtype=float32>

```