<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.datasets.cifar100.load_data" />
</div>

# tf.contrib.keras.datasets.cifar100.load_data

``` python
load_data(label_mode='fine')
```



Defined in [`tensorflow/contrib/keras/python/keras/datasets/cifar100.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/datasets/cifar100.py).

Loads CIFAR100 dataset.

#### Arguments:

    label_mode: one of "fine", "coarse".


#### Returns:

    Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.


#### Raises:

    ValueError: in case of invalid `label_mode`.