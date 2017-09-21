<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.conv1d" />
</div>

# tf.contrib.keras.backend.conv1d

``` python
conv1d(
    x,
    kernel,
    strides=1,
    padding='valid',
    data_format=None,
    dilation_rate=1
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

1D convolution.

#### Arguments:

    x: Tensor or variable.
    kernel: kernel tensor.
    strides: stride integer.
    padding: string, `"same"`, `"causal"` or `"valid"`.
    data_format: string, one of "channels_last", "channels_first".
    dilation_rate: integer dilate rate.


#### Returns:

    A tensor, result of 1D convolution.