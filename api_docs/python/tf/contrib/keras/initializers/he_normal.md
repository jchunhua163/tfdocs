<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.initializers.he_normal" />
</div>

# tf.contrib.keras.initializers.he_normal

``` python
he_normal(seed=None)
```



Defined in [`tensorflow/contrib/keras/python/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/initializers.py).

He normal initializer.

It draws samples from a truncated normal distribution centered on 0
with `stddev = sqrt(2 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

    seed: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    He et al., http://arxiv.org/abs/1502.01852