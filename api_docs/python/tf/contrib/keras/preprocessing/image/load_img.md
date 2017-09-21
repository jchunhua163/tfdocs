<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.preprocessing.image.load_img" />
</div>

# tf.contrib.keras.preprocessing.image.load_img

``` python
load_img(
    path,
    grayscale=False,
    target_size=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/preprocessing/image.py).

Loads an image into PIL format.

#### Arguments:

    path: Path to image file
    grayscale: Boolean, whether to load the image as grayscale.
    target_size: Either `None` (default to original size)
        or tuple of ints `(img_height, img_width)`.


#### Returns:

    A PIL Image instance.


#### Raises:

    ImportError: if PIL is not available.