<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.errors.OutOfRangeError" />
<meta itemprop="property" content="error_code"/>
<meta itemprop="property" content="message"/>
<meta itemprop="property" content="node_def"/>
<meta itemprop="property" content="op"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.errors.OutOfRangeError

## Class `OutOfRangeError`

Inherits From: [`OpError`](../../tf/OpError.md)



Defined in [`tensorflow/python/framework/errors_impl.py`](https://www.tensorflow.org/code/tensorflow/python/framework/errors_impl.py).

See the guides: [Reading data > Reading from files](../../../../api_guides/python/reading_data.md#Reading_from_files), [Running Graphs > Error classes and convenience functions](../../../../api_guides/python/client.md#Error_classes_and_convenience_functions)

Raised when an operation iterates past the valid input range.

This exception is raised in "end-of-file" conditions, such as when a
[`tf.QueueBase.dequeue`](../../tf/QueueBase.md#dequeue)
operation is blocked on an empty queue, and a
[`tf.QueueBase.close`](../../tf/QueueBase.md#close)
operation executes.


## Properties

<h3 id="error_code"><code>error_code</code></h3>

The integer error code that describes the error.

<h3 id="message"><code>message</code></h3>

The error message that describes the error.

<h3 id="node_def"><code>node_def</code></h3>

The `NodeDef` proto representing the op that failed.

<h3 id="op"><code>op</code></h3>

The operation that failed, if known.

*N.B.* If the failed op was synthesized at runtime, e.g. a `Send`
or `Recv` op, there will be no corresponding
[`tf.Operation`](../../tf/Operation.md)
object.  In that case, this will return `None`, and you should
instead use the [`tf.OpError.node_def`](../../tf/OpError.md#node_def) to
discover information about the op.

#### Returns:

  The `Operation` that failed, or None.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    node_def,
    op,
    message
)
```

Creates an `OutOfRangeError`.



