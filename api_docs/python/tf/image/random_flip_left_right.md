<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_flip_left_right" />
</div>

# tf.image.random_flip_left_right

``` python
random_flip_left_right(
    image,
    seed=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Flipping, Rotating and Transposing](../../../../api_guides/python/image.md#Flipping_Rotating_and_Transposing)

Randomly flip an image horizontally (left to right).

With a 1 in 2 chance, outputs the contents of `image` flipped along the
second dimension, which is `width`.  Otherwise output the image as-is.

#### Args:

* <b>`image`</b>: A 3-D tensor of shape `[height, width, channels].`
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
    [`tf.set_random_seed`](../../tf/set_random_seed.md)
    for behavior.


#### Returns:

  A 3-D tensor of the same type and shape as `image`.


#### Raises:

* <b>`ValueError`</b>: if the shape of `image` not supported.