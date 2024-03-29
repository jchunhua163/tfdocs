<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_session_handle" />
</div>

# tf.get_session_handle

``` python
get_session_handle(
    data,
    name=None
)
```



Defined in [`tensorflow/python/ops/session_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/session_ops.py).

See the guide: [Tensor Handle Operations > Tensor Handle Operations](../../../api_guides/python/session_ops.md#Tensor_Handle_Operations)

Return the handle of `data`.

This is EXPERIMENTAL and subject to change.

Keep `data` "in-place" in the runtime and create a handle that can be
used to retrieve `data` in a subsequent run().

Combined with `get_session_tensor`, we can keep a tensor produced in
one run call in place, and use it as the input in a future run call.

#### Args:

* <b>`data`</b>: A tensor to be stored in the session.
* <b>`name`</b>: Optional name prefix for the return tensor.


#### Returns:

  A scalar string tensor representing a unique handle for `data`.


#### Raises:

* <b>`TypeError`</b>: if `data` is not a Tensor.

Example:

```python
c = tf.multiply(a, b)
h = tf.get_session_handle(c)
h = sess.run(h)

p, a = tf.get_session_tensor(h.handle, tf.float32)
b = tf.multiply(a, 10)
c = sess.run(b, feed_dict={p: h.handle})
```