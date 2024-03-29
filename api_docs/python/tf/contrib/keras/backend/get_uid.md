<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.get_uid" />
</div>

# tf.contrib.keras.backend.get_uid

``` python
get_uid(prefix='')
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Associates a string prefix with an integer counter in a TensorFlow graph.

#### Arguments:

* <b>`prefix`</b>: String prefix to index.


#### Returns:

  Unique integer ID.

Example:

```
  >>> get_uid('dense')
  1
  >>> get_uid('dense')
  2
```