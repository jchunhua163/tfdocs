<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.initializers.he_uniform" />
</div>

# tf.contrib.keras.initializers.he_uniform

``` python
he_uniform(seed=None)
```



Defined in [`tensorflow/contrib/keras/python/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/initializers.py).

He uniform variance scaling initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

    seed: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    He et al., http://arxiv.org/abs/1502.01852