<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.initializers.Identity" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.contrib.keras.initializers.Identity

## Class `Identity`

Inherits From: [`Initializer`](../../../../tf/contrib/keras/initializers/Initializer.md)



Defined in [`tensorflow/contrib/keras/python/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/initializers.py).

Initializer that generates the identity matrix.

Only use for square 2D matrices.

#### Arguments:

    gain: Multiplicative factor to apply to the identity matrix.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(gain=1.0)
```



<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None
)
```



<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.

Example:

```
initializer = RandomUniform(-1, 1)
config = initializer.get_config()
initializer = RandomUniform.from_config(config)
```

#### Arguments:

* <b>`config`</b>: A Python dictionary.
    It will typically be the output of `get_config`.


#### Returns:

  An Initializer instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```





