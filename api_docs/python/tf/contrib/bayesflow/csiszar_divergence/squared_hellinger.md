<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.bayesflow.csiszar_divergence.squared_hellinger" />
</div>

# tf.contrib.bayesflow.csiszar_divergence.squared_hellinger

``` python
squared_hellinger(
    logu,
    name=None
)
```



Defined in [`tensorflow/contrib/bayesflow/python/ops/csiszar_divergence_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/bayesflow/python/ops/csiszar_divergence_impl.py).

The Squared-Hellinger Csiszar-function in log-space.

A Csiszar-function is a member of,

```none
F = { f:R_+ to R : f convex }.
```

The Squared-Hellinger Csiszar-function is:

```none
f(u) = (sqrt(u) - 1)**2
```

This Csiszar-function induces a symmetric f-Divergence, i.e.,
`D_f[p, q] = D_f[q, p]`.

Warning: this function makes non-log-space calculations and may therefore be
numerically unstable for `|logu| >> 0`.

#### Args:

* <b>`logu`</b>: Floating-type `Tensor` representing `log(u)` from above.
* <b>`name`</b>: Python `str` name prefixed to Ops created by this function.


#### Returns:

* <b>`squared_hellinger_of_u`</b>: Floating-type `Tensor` of the Csiszar-function
    evaluated at `u = exp(logu)`.