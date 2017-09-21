<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.ctc_label_dense_to_sparse" />
</div>

# tf.contrib.keras.backend.ctc_label_dense_to_sparse

``` python
ctc_label_dense_to_sparse(
    labels,
    label_lengths
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Converts CTC labels from dense to sparse.

#### Arguments:

    labels: dense CTC labels.
    label_lengths: length of the labels.


#### Returns:

    A sparse tensor representation of the lablels.