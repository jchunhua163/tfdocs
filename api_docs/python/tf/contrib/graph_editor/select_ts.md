<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.select_ts" />
</div>

# tf.contrib.graph_editor.select_ts

``` python
select_ts(
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

See the guide: [Graph Editor (contrib) > Module: select](../../../../../api_guides/python/contrib.graph_editor.md#Module_select)

Helper to select tensors.

#### Args:

  *args: list of 1) regular expressions (compiled or not) or  2) (array of)
    `tf.Tensor`. `tf.Operation` instances are silently ignored.
  **kwargs: 'graph': `tf.Graph` in which to perform the regex query.This is
    required when using regex.
    'positive_filter': an elem if selected only if `positive_filter(elem)` is
      `True`. This is optional.
    'restrict_ts_regex': a regular expression is ignored if it doesn't start
      with the substring "(?#ts)".

#### Returns:

  A list of `tf.Tensor`.

#### Raises:

* <b>`TypeError`</b>: if the optional keyword argument graph is not a `tf.Graph`
    or if an argument in args is not an (array of) `tf.Tensor`
    or an (array of) `tf.Operation` (silently ignored) or a string
    or a regular expression.
* <b>`ValueError`</b>: if one of the keyword arguments is unexpected or if a regular
    expression is used without passing a graph as a keyword argument.