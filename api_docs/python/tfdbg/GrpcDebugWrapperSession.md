<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfdbg.GrpcDebugWrapperSession" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="graph_def"/>
<meta itemprop="property" content="sess_str"/>
<meta itemprop="property" content="session"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_default"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="invoke_node_stepper"/>
<meta itemprop="property" content="list_devices"/>
<meta itemprop="property" content="make_callable"/>
<meta itemprop="property" content="on_run_end"/>
<meta itemprop="property" content="on_run_start"/>
<meta itemprop="property" content="on_session_init"/>
<meta itemprop="property" content="partial_run"/>
<meta itemprop="property" content="partial_run_setup"/>
<meta itemprop="property" content="prepare_run_debug_urls"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="run"/>
</div>

# tfdbg.GrpcDebugWrapperSession

## Class `GrpcDebugWrapperSession`





Defined in [`tensorflow/python/debug/wrappers/grpc_wrapper.py`](https://www.tensorflow.org/code/tensorflow/python/debug/wrappers/grpc_wrapper.py).

Debug Session wrapper that send debug data to gRPC stream(s).

## Properties

<h3 id="graph"><code>graph</code></h3>



<h3 id="graph_def"><code>graph_def</code></h3>



<h3 id="sess_str"><code>sess_str</code></h3>



<h3 id="session"><code>session</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    sess,
    grpc_debug_server_addresses,
    watch_fn=None,
    thread_name_filter=None,
    log_usage=True
)
```

Constructor of DumpingDebugWrapperSession.

#### Args:

* <b>`sess`</b>: The TensorFlow `Session` object being wrapped.
* <b>`grpc_debug_server_addresses`</b>: (`str` or `list` of `str`) Single or a list
    of the gRPC debug server addresses, in the format of
    <host:port>, without the "grpc://" prefix. For example:
      "localhost:7000",
      ["localhost:7000", "192.168.0.2:8000"]
* <b>`watch_fn`</b>: (`Callable`) A Callable that can be used to define per-run
    debug ops and watched tensors. See the doc of
    `NonInteractiveDebugWrapperSession.__init__()` for details.
* <b>`thread_name_filter`</b>: Regular-expression white list for threads on which the
    wrapper session will be active. See doc of `BaseDebugWrapperSession` for
    more details.
* <b>`log_usage`</b>: (`bool`) whether the usage of this class is to be logged.


#### Raises:

   TypeError: If `grpc_debug_server_addresses` is not a `str` or a `list`
     of `str`.

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```



<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    exec_type,
    exec_value,
    exec_tb
)
```



<h3 id="as_default"><code>as_default</code></h3>

``` python
as_default()
```



<h3 id="close"><code>close</code></h3>

``` python
close()
```



<h3 id="invoke_node_stepper"><code>invoke_node_stepper</code></h3>

``` python
invoke_node_stepper(
    node_stepper,
    restore_variable_values_on_exit=True
)
```

See doc of BaseDebugWrapperSession.invoke_node_stepper.

<h3 id="list_devices"><code>list_devices</code></h3>

``` python
list_devices(
    *args,
    **kwargs
)
```



<h3 id="make_callable"><code>make_callable</code></h3>

``` python
make_callable(
    fetches,
    feed_list=None,
    accept_options=False
)
```



<h3 id="on_run_end"><code>on_run_end</code></h3>

``` python
on_run_end(request)
```

See doc of BaseDebugWrapperSession.on_run_end.

<h3 id="on_run_start"><code>on_run_start</code></h3>

``` python
on_run_start(request)
```

See doc of BaseDebugWrapperSession.on_run_start.

<h3 id="on_session_init"><code>on_session_init</code></h3>

``` python
on_session_init(request)
```

See doc of BaseDebugWrapperSession.on_run_start.

<h3 id="partial_run"><code>partial_run</code></h3>

``` python
partial_run(
    handle,
    fetches,
    feed_dict=None
)
```



<h3 id="partial_run_setup"><code>partial_run_setup</code></h3>

``` python
partial_run_setup(
    fetches,
    feeds=None
)
```

Sets up the feeds and fetches for partial runs in the session.

<h3 id="prepare_run_debug_urls"><code>prepare_run_debug_urls</code></h3>

``` python
prepare_run_debug_urls(
    fetches,
    feed_dict
)
```

Implementation of abstract method in superclass.

See doc of `NonInteractiveDebugWrapperSession.prepare_run_debug_urls()`
for details.

#### Args:

* <b>`fetches`</b>: Same as the `fetches` argument to `Session.run()`
* <b>`feed_dict`</b>: Same as the `feed_dict` argument to `Session.run()`


#### Returns:

* <b>`debug_urls`</b>: (`str` or `list` of `str`) file:// debug URLs to be used in
    this `Session.run()` call.

<h3 id="reset"><code>reset</code></h3>

``` python
reset(
    *args,
    **kwargs
)
```



<h3 id="run"><code>run</code></h3>

``` python
run(
    fetches,
    feed_dict=None,
    options=None,
    run_metadata=None,
    callable_runner=None,
    callable_runner_args=None
)
```

Wrapper around Session.run() that inserts tensor watch options.

#### Args:

* <b>`fetches`</b>: Same as the `fetches` arg to regular `Session.run()`.
* <b>`feed_dict`</b>: Same as the `feed_dict` arg to regular `Session.run()`.
* <b>`options`</b>: Same as the `options` arg to regular `Session.run()`.
* <b>`run_metadata`</b>: Same as the `run_metadata` arg to regular `Session.run()`.
* <b>`callable_runner`</b>: A `callable` returned by `Session.make_callable()`.
    If not `None`, `fetches` and `feed_dict` must both be `None`.
* <b>`callable_runner_args`</b>: An optional list of arguments to `callable_runner`.


#### Returns:

  Simply forwards the output of the wrapped `Session.run()` call.


#### Raises:

* <b>`ValueError`</b>: On invalid `OnRunStartAction` value. Or if `callable_runner`
    is not `None` and either or both of `fetches` and `feed_dict` is `None`.



