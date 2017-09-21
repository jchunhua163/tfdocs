<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.utils.to_categorical" />
</div>

# tf.contrib.keras.utils.to_categorical

``` python
to_categorical(
    y,
    num_classes=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/utils/np_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/utils/np_utils.py).

Converts a class vector (integers) to binary class matrix.

E.g. for use with categorical_crossentropy.

#### Arguments:

    y: class vector to be converted into a matrix
        (integers from 0 to num_classes).
    num_classes: total number of classes.


#### Returns:

    A binary matrix representation of the input.