<!-- DO NOT EDIT! Automatically generated file. -->
# Frequently Asked Questions

This document provides answers to some of the frequently asked questions about
TensorFlow. If you have a question that is not covered here, you might find an
answer on one of the TensorFlow [community resources](../about/index.md).

[TOC]

## Features and Compatibility

#### Can I run distributed training on multiple computers?

Yes! TensorFlow gained
[support for distributed computation](../deploy/distributed.md) in
version 0.8. TensorFlow now supports multiple devices (CPUs and GPUs) in one or
more computers.

#### Does TensorFlow work with Python 3?

As of the 0.6.0 release timeframe (Early December 2015), we do support Python
3.3+.

## Building a TensorFlow graph

See also the
[API documentation on building graphs](../api_guides/python/framework.md).

#### Why does `c = tf.matmul(a, b)` not execute the matrix multiplication immediately?

In the TensorFlow Python API, `a`, `b`, and `c` are
[`tf.Tensor`](../api_docs/python/tf/Tensor.md) objects. A `Tensor` object is
a symbolic handle to the result of an operation, but does not actually hold the
values of the operation's output. Instead, TensorFlow encourages users to build
up complicated expressions (such as entire neural networks and its gradients) as
a dataflow graph. You then offload the computation of the entire dataflow graph
(or a subgraph of it) to a TensorFlow
[`tf.Session`](../api_docs/python/tf/Session.md), which is able to execute the
whole computation much more efficiently than executing the operations
one-by-one.

#### How are devices named?

The supported device names are `"/device:CPU:0"` (or `"/cpu:0"`) for the CPU
device, and `"/device:GPU:i"` (or `"/gpu:i"`) for the *i*th GPU device.

#### How do I place operations on a particular device?

To place a group of operations on a device, create them within a
[`with tf.device(name):`](../api_docs/python/tf/device.md) context.  See
the how-to documentation on
[using GPUs with TensorFlow](../tutorials/using_gpu.md) for details of how
TensorFlow assigns operations to devices, and the
[CIFAR-10 tutorial](../tutorials/deep_cnn.md) for an example model that
uses multiple GPUs.


## Running a TensorFlow computation

See also the
[API documentation on running graphs](../api_guides/python/client.md).

#### What's the deal with feeding and placeholders?

Feeding is a mechanism in the TensorFlow Session API that allows you to
substitute different values for one or more tensors at run time. The `feed_dict`
argument to [`tf.Session.run`](../api_docs/python/tf/Session.md#run) is a
dictionary that maps [`tf.Tensor`](../api_docs/python/tf/Tensor.md) objects to
numpy arrays (and some other types), which will be used as the values of those
tensors in the execution of a step.

Often, you have certain tensors, such as inputs, that will always be fed. The
[`tf.placeholder`](../api_docs/python/tf/placeholder.md) op allows you
to define tensors that *must* be fed, and optionally allows you to constrain
their shape as well. See the
[beginners' MNIST tutorial](../get_started/mnist/beginners.md) for an
example of how placeholders and feeding can be used to provide the training data
for a neural network.

#### What is the difference between `Session.run()` and `Tensor.eval()`?

If `t` is a [`tf.Tensor`](../api_docs/python/tf/Tensor.md) object,
[`tf.Tensor.eval`](../api_docs/python/tf/Tensor.md#eval) is shorthand for
[`tf.Session.run`](../api_docs/python/tf/Session.md#run) (where `sess` is the
current [`tf.get_default_session`](../api_docs/python/tf/get_default_session.md). The
two following snippets of code are equivalent:

```python
# Using `Session.run()`.
sess = tf.Session()
c = tf.constant(5.0)
print(sess.run(c))

# Using `Tensor.eval()`.
c = tf.constant(5.0)
with tf.Session():
  print(c.eval())
```

In the second example, the session acts as a
[context manager](https://docs.python.org/2.7/reference/compound_stmts.html#with),
which has the effect of installing it as the default session for the lifetime of
the `with` block. The context manager approach can lead to more concise code for
simple use cases (like unit tests); if your code deals with multiple graphs and
sessions, it may be more straightforward to make explicit calls to
`Session.run()`.

#### Do Sessions have a lifetime? What about intermediate tensors?

Sessions can own resources, such as
[`tf.Variable`](../api_docs/python/tf/Variable.md),
[`tf.QueueBase`](../api_docs/python/tf/QueueBase.md), and
[`tf.ReaderBase`](../api_docs/python/tf/ReaderBase.md); and these resources can use
a significant amount of memory. These resources (and the associated memory) are
released when the session is closed, by calling
[`tf.Session.close`](../api_docs/python/tf/Session.md#close).

The intermediate tensors that are created as part of a call to
[`Session.run()`](../api_guides/python/client.md) will be freed at or before the
end of the call.

#### Does the runtime parallelize parts of graph execution?

The TensorFlow runtime parallelizes graph execution across many different
dimensions:

* The individual ops have parallel implementations, using multiple cores in a
  CPU, or multiple threads in a GPU.
* Independent nodes in a TensorFlow graph can run in parallel on multiple
  devices, which makes it possible to speed up
  [CIFAR-10 training using multiple GPUs](../tutorials/deep_cnn.md).
* The Session API allows multiple concurrent steps (i.e. calls to
  [`tf.Session.run`](../api_docs/python/tf/Session.md#run) in parallel. This
  enables the runtime to get higher throughput, if a single step does not use
  all of the resources in your computer.

#### Which client languages are supported in TensorFlow?

TensorFlow is designed to support multiple client languages.
Currently, the best-supported client language is [Python](../api_docs/python/index.md). Experimental interfaces for
executing and constructing graphs are also available for
[C++](../api_docs/cc/index.md), [Java](../api_docs/java/reference/org/tensorflow/package-summary.html) and [Go](https://godoc.org/github.com/tensorflow/tensorflow/tensorflow/go).

TensorFlow also has a
[C-based client API](https://www.tensorflow.org/code/tensorflow/c/c_api.h)
to help build support for more client languages.  We invite contributions of new
language bindings.

Bindings for various other languages (such as [C#](https://github.com/migueldeicaza/TensorFlowSharp), [Julia](https://github.com/malmaud/TensorFlow.jl), [Ruby](https://github.com/somaticio/tensorflow.rb) and [Scala](https://github.com/eaplatanios/tensorflow_scala)) created and supported by the opensource community build on top of the C API supported by the TensorFlow maintainers.

#### Does TensorFlow make use of all the devices (GPUs and CPUs) available on my machine?

TensorFlow supports multiple GPUs and CPUs. See the how-to documentation on
[using GPUs with TensorFlow](../tutorials/using_gpu.md) for details of how
TensorFlow assigns operations to devices, and the
[CIFAR-10 tutorial](../tutorials/deep_cnn.md) for an example model that
uses multiple GPUs.

Note that TensorFlow only uses GPU devices with a compute capability greater
than 3.5.

#### Why does `Session.run()` hang when using a reader or a queue?

The [`tf.ReaderBase`](../api_docs/python/tf/ReaderBase.md) and
[`tf.QueueBase`](../api_docs/python/tf/QueueBase.md) classes provide special operations that
can *block* until input (or free space in a bounded queue) becomes
available. These operations allow you to build sophisticated
[input pipelines](../api_guides/python/reading_data.md), at the cost of making the
TensorFlow computation somewhat more complicated. See the how-to documentation
for
[using
`QueueRunner` objects to drive queues and readers](../api_guides/python/reading_data.md#creating-threads-to-prefetch-using-queuerunner-objects)
for more information on how to use them.

## Variables

See also the how-to documentation on [variables](../programmers_guide/variables.md) and
[the API documentation for variables](../api_guides/python/state_ops.md).

#### What is the lifetime of a variable?

A variable is created when you first run the
[`tf.Variable.initializer`](../api_docs/python/tf/Variable.md#initializer)
operation for that variable in a session. It is destroyed when that
[`tf.Session.close`](../api_docs/python/tf/Session.md#close).

#### How do variables behave when they are concurrently accessed?

Variables allow concurrent read and write operations. The value read from a
variable may change if it is concurrently updated. By default, concurrent
assignment operations to a variable are allowed to run with no mutual exclusion.
To acquire a lock when assigning to a variable, pass `use_locking=True` to
[`tf.Variable.assign`](../api_docs/python/tf/Variable.md#assign).

## Tensor shapes

See also the
[`tf.TensorShape`](../api_docs/python/tf/TensorShape.md).

#### How can I determine the shape of a tensor in Python?

In TensorFlow, a tensor has both a static (inferred) shape and a dynamic (true)
shape. The static shape can be read using the
[`tf.Tensor.get_shape`](../api_docs/python/tf/Tensor.md#get_shape)
method: this shape is inferred from the operations that were used to create the
tensor, and may be
[partially complete](../api_docs/python/tf/TensorShape.md). If the static
shape is not fully defined, the dynamic shape of a `Tensor` `t` can be
determined by evaluating [`tf.shape(t)`](../api_docs/python/tf/shape.md).

#### What is the difference between `x.set_shape()` and `x = tf.reshape(x)`?

The [`tf.Tensor.set_shape`](../api_docs/python/tf/Tensor.md#set_shape) method updates
the static shape of a `Tensor` object, and it is typically used to provide
additional shape information when this cannot be inferred directly. It does not
change the dynamic shape of the tensor.

The [`tf.reshape`](../api_docs/python/tf/reshape.md) operation creates
a new tensor with a different dynamic shape.

#### How do I build a graph that works with variable batch sizes?

It is often useful to build a graph that works with variable batch sizes, for
example so that the same code can be used for (mini-)batch training, and
single-instance inference. The resulting graph can be
[saved as a protocol buffer](../api_docs/python/tf/Graph.md#as_graph_def)
and
[imported into another program](../api_docs/python/tf/import_graph_def.md).

When building a variable-size graph, the most important thing to remember is not
to encode the batch size as a Python constant, but instead to use a symbolic
`Tensor` to represent it. The following tips may be useful:

* Use [`batch_size = tf.shape(input)[0]`](../api_docs/python/array_ops.md#shape)
  to extract the batch dimension from a `Tensor` called `input`, and store it in
  a `Tensor` called `batch_size`.

* Use [`tf.reduce_mean`](../api_docs/python/tf/reduce_mean.md) instead
  of `tf.reduce_sum(...) / batch_size`.


## TensorBoard

#### How can I visualize a TensorFlow graph?

See the [graph visualization tutorial](../get_started/graph_viz.md).

#### What is the simplest way to send data to TensorBoard?

Add summary ops to your TensorFlow graph, and write
these summaries to a log directory.  Then, start TensorBoard using

    python tensorflow/tensorboard/tensorboard.py --logdir=path/to/log-directory

For more details, see the
[Summaries and TensorBoard tutorial](../get_started/summaries_and_tensorboard.md).

#### Every time I launch TensorBoard, I get a network security popup!

You can change TensorBoard to serve on localhost rather than '0.0.0.0' by
the flag --host=localhost. This should quiet any security warnings.

## Extending TensorFlow

See the how-to documentation for
[adding a new operation to TensorFlow](../extend/adding_an_op.md).

#### My data is in a custom format. How do I read it using TensorFlow?

There are three main options for dealing with data in a custom format.

The easiest option is to write parsing code in Python that transforms the data
into a numpy array. Then use [`tf.contrib.data.Dataset.from_tensor_slices`](../api_docs/python/tf/contrib/data/Dataset.md#from_tensor_slices) to
create an input pipeline from the in-memory data.

If your data doesn't fit in memory, try doing the parsing in the Dataset
pipeline. Start with an appropriate file reader, like
[`tf.contrib.data.TextLineDataset`](../api_docs/python/tf/contrib/data/TextLineDataset.md). Then convert the dataset by mapping
[mapping](../api_docs/python/tf/contrib/data/Dataset.md#map) appropriate operations over it.
Prefer predefined TensorFlow operations such as [`tf.decode_raw`](../api_docs/python/tf/decode_raw.md),
[`tf.decode_csv`](../api_docs/python/tf/decode_csv.md), [`tf.parse_example`](../api_docs/python/tf/parse_example.md), or [`tf.image.decode_png`](../api_docs/python/tf/image/decode_png.md).

If your data is not easily parsable with the built-in TensorFlow operations,
consider converting it, offline, to a format that is easily parsable, such
as ${tf.python_io.TFRecordWriter$`TFRecord`} format.

The more efficient method to customize the parsing behavior is to
[add a new op written in C++](../extend/adding_an_op.md) that parses your
data format. The [guide to handling new data formats](../extend/new_data_formats.md) has
more information about the steps for doing this.


## Miscellaneous

#### What is TensorFlow's coding style convention?

The TensorFlow Python API adheres to the
[PEP8](https://www.python.org/dev/peps/pep-0008/) conventions.<sup>*</sup> In
particular, we use `CamelCase` names for classes, and `snake_case` names for
functions, methods, and properties. We also adhere to the
[Google Python style guide](https://google.github.io/styleguide/pyguide.html).

The TensorFlow C++ code base adheres to the
[Google C++ style guide](http://google.github.io/styleguide/cppguide.html).

(<sup>*</sup> With one exception: we use 2-space indentation instead of 4-space
indentation.)

