<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.datasets.boston_housing.load_data" />
</div>

# tf.contrib.keras.datasets.boston_housing.load_data

``` python
load_data(
    path='boston_housing.npz',
    seed=113,
    test_split=0.2
)
```



Defined in [`tensorflow/contrib/keras/python/keras/datasets/boston_housing.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/datasets/boston_housing.py).

Loads the Boston Housing dataset.

#### Arguments:

    path: path where to cache the dataset locally
        (relative to ~/.keras/datasets).
    seed: Random seed for shuffling the data
        before computing the test split.
    test_split: fraction of the data to reserve as test set.


#### Returns:

    Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.