<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.CustomHelper" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="next_inputs"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.seq2seq.CustomHelper

## Class `CustomHelper`

Inherits From: [`Helper`](../../../tf/contrib/seq2seq/Helper.md)



Defined in [`tensorflow/contrib/seq2seq/python/ops/helper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/helper.py).

See the guide: [Seq2seq Library (contrib) > Dynamic Decoding](../../../../../api_guides/python/contrib.seq2seq.md#Dynamic_Decoding)

Base abstract class that allows the user to customize sampling.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    initialize_fn,
    sample_fn,
    next_inputs_fn
)
```

Initializer.

#### Args:

* <b>`initialize_fn`</b>: callable that returns `(finished, next_inputs)`
    for the first iteration.
* <b>`sample_fn`</b>: callable that takes `(time, outputs, state)`
    and emits tensor `sample_ids`.
* <b>`next_inputs_fn`</b>: callable that takes `(time, outputs, state, sample_ids)`
    and emits `(finished, next_inputs, next_state)`.

<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(name=None)
```



<h3 id="next_inputs"><code>next_inputs</code></h3>

``` python
next_inputs(
    time,
    outputs,
    state,
    sample_ids,
    name=None
)
```



<h3 id="sample"><code>sample</code></h3>

``` python
sample(
    time,
    outputs,
    state,
    name=None
)
```





