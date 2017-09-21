<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.ServingInputReceiver" />
<meta itemprop="property" content="features"/>
<meta itemprop="property" content="receiver_tensors"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.estimator.export.ServingInputReceiver

## Class `ServingInputReceiver`





Defined in [`tensorflow/python/estimator/export/export.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/export/export.py).

A return type for a serving_input_receiver_fn.

The expected return values are:
  features: A dict of string to `Tensor` or `SparseTensor`, specifying the
    features to be passed to the model.
  receiver_tensors: a `Tensor`, or a dict of string to `Tensor`, specifying
    input nodes where this receiver expects to be fed.  Typically, this is a
    single placeholder expecting serialized `tf.Example` protos.

## Properties

<h3 id="features"><code>features</code></h3>

Alias for field number 0

<h3 id="receiver_tensors"><code>receiver_tensors</code></h3>

Alias for field number 1



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    cls,
    features,
    receiver_tensors
)
```





