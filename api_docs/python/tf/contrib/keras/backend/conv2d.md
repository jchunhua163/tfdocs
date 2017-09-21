<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.conv2d" />
</div>

# tf.contrib.keras.backend.conv2d

``` python
conv2d(
    x,
    kernel,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1)
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

2D convolution.

#### Arguments:

    x: Tensor or variable.
    kernel: kernel tensor.
    strides: strides tuple.
    padding: string, `"same"` or `"valid"`.
    data_format: `"channels_last"` or `"channels_first"`.
        Whether to use Theano or TensorFlow data format
        for inputs/kernels/outputs.
    dilation_rate: tuple of 2 integers.


#### Returns:

    A tensor, result of 2D convolution.


#### Raises:

    ValueError: if `data_format` is neither `channels_last` or
    `channels_first`.