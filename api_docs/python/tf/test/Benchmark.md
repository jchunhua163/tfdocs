<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.Benchmark" />
<meta itemprop="property" content="is_abstract"/>
<meta itemprop="property" content="report_benchmark"/>
<meta itemprop="property" content="run_op_benchmark"/>
</div>

# tf.test.Benchmark

## Class `Benchmark`





Defined in [`tensorflow/python/platform/benchmark.py`](https://www.tensorflow.org/code/tensorflow/python/platform/benchmark.py).

Abstract class that provides helpers for TensorFlow benchmarks.

## Methods

<h3 id="is_abstract"><code>is_abstract</code></h3>

``` python
is_abstract(cls)
```



<h3 id="report_benchmark"><code>report_benchmark</code></h3>

``` python
report_benchmark(
    iters=None,
    cpu_time=None,
    wall_time=None,
    throughput=None,
    extras=None,
    name=None
)
```

Report a benchmark.

#### Args:

* <b>`iters`</b>: (optional) How many iterations were run
* <b>`cpu_time`</b>: (optional) Total cpu time in seconds
* <b>`wall_time`</b>: (optional) Total wall time in seconds
* <b>`throughput`</b>: (optional) Throughput (in MB/s)
* <b>`extras`</b>: (optional) Dict mapping string keys to additional benchmark info.
    Values may be either floats or values that are convertible to strings.
* <b>`name`</b>: (optional) Override the BenchmarkEntry name with `name`.
    Otherwise it is inferred from the top-level method name.

<h3 id="run_op_benchmark"><code>run_op_benchmark</code></h3>

``` python
run_op_benchmark(
    sess,
    op_or_tensor,
    feed_dict=None,
    burn_iters=2,
    min_iters=10,
    store_trace=False,
    store_memory_usage=True,
    name=None,
    extras=None,
    mbs=0
)
```

Run an op or tensor in the given session.  Report the results.

#### Args:

* <b>`sess`</b>: `Session` object to use for timing.
* <b>`op_or_tensor`</b>: `Operation` or `Tensor` to benchmark.
* <b>`feed_dict`</b>: A `dict` of values to feed for each op iteration (see the
    `feed_dict` parameter of `Session.run`).
* <b>`burn_iters`</b>: Number of burn-in iterations to run.
* <b>`min_iters`</b>: Minimum number of iterations to use for timing.
* <b>`store_trace`</b>: Boolean, whether to run an extra untimed iteration and
    store the trace of iteration in the benchmark report.
    The trace will be stored as a string in Google Chrome trace format
    in the extras field "full_trace_chrome_format".
* <b>`store_memory_usage`</b>: Boolean, whether to run an extra
    untimed iteration, calculate memory usage, and store that in extras
    fields.
* <b>`name`</b>: (optional) Override the BenchmarkEntry name with `name`.
    Otherwise it is inferred from the top-level method name.
* <b>`extras`</b>: (optional) Dict mapping string keys to additional benchmark info.
    Values may be either floats or values that are convertible to strings.
* <b>`mbs`</b>: (optional) The number of megabytes moved by this op, used to
    calculate the ops throughput.


#### Returns:

  A `dict` containing the key-value pairs that were passed to
  `report_benchmark`.



