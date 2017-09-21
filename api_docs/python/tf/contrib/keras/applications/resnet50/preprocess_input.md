<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.applications.resnet50.preprocess_input" />
</div>

# tf.contrib.keras.applications.resnet50.preprocess_input

### Aliases:

* `tf.contrib.keras.applications.resnet50.preprocess_input`
* `tf.contrib.keras.applications.vgg16.preprocess_input`
* `tf.contrib.keras.applications.vgg19.preprocess_input`

``` python
preprocess_input(
    x,
    data_format=None
)
```



Defined in [`tensorflow/contrib/keras/python/keras/applications/imagenet_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/applications/imagenet_utils.py).

Preprocesses a tensor encoding a batch of images.

#### Arguments:

    x: input Numpy tensor, 4D.
    data_format: data format of the image tensor.


#### Returns:

    Preprocessed tensor.