<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors.SinhArcsinh" />
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="event_ndims"/>
<meta itemprop="property" content="graph_parents"/>
<meta itemprop="property" content="is_constant_jacobian"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="skewness"/>
<meta itemprop="property" content="tailweight"/>
<meta itemprop="property" content="validate_args"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="forward"/>
<meta itemprop="property" content="forward_event_shape"/>
<meta itemprop="property" content="forward_event_shape_tensor"/>
<meta itemprop="property" content="forward_log_det_jacobian"/>
<meta itemprop="property" content="inverse"/>
<meta itemprop="property" content="inverse_event_shape"/>
<meta itemprop="property" content="inverse_event_shape_tensor"/>
<meta itemprop="property" content="inverse_log_det_jacobian"/>
</div>

# tf.contrib.distributions.bijectors.SinhArcsinh

## Class `SinhArcsinh`

Inherits From: [`Bijector`](../../../../tf/distributions/bijectors/Bijector.md)



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/sinh_arcsinh_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/python/ops/bijectors/sinh_arcsinh_impl.py).

Compute `Y = g(X) = Sinh( (Arcsinh(X) + skewness) * tailweight )`.

For `skewness in (-inf, inf)` and `tailweight in (0, inf)`, this
transformation is a
diffeomorphism of the real line `(-inf, inf)`.  The inverse transform is
`X = g^{-1}(Y) = Sinh( ArcSinh(Y) / tailweight - skewness )`.

The `SinhArcsinh` transformation of the Normal is described in
[Sinh-arcsinh distributions](https://www.jstor.org/stable/27798865)
This Bijector allows a similar transformation of any distribution supported on
`(-inf, inf)`.

#### Meaning of the parameters

* If `skewness = 0` and `tailweight = 1`, this transform is the identity.
* Positive (negative) `skewness` leads to positive (negative) skew.
  * positive skew means, for unimodal `X` centered at zero, the mode of `Y` is
    "tilted" to the right.
  * positive skew means positive values of `Y` become more likely, and
    negative values become less likely.
* Larger (smaller) `tailweight` leads to fatter (thinner) tails.
  * Fatter tails mean larger values of `|Y|` become more likely.
  * If `X` is a unit Normal, `tailweight < 1` leads to a distribution that is
    "flat" around `Y = 0`, and a very steep drop-off in the tails.
  * If `X` is a unit Normal, `tailweight > 1` leads to a distribution more
    peaked at the mode with heavier tails.

To see the argument about the tails, note that for `|X| >> 1` and
`|X| >> (|skewness| * tailweight)**tailweight`, we have
`Y approx 0.5 X**tailweight e**(sign(X) skewness * tailweight)`.

## Properties

<h3 id="dtype"><code>dtype</code></h3>

dtype of `Tensor`s transformable by this distribution.

<h3 id="event_ndims"><code>event_ndims</code></h3>

Returns then number of event dimensions this bijector operates on.

<h3 id="graph_parents"><code>graph_parents</code></h3>

Returns this `Bijector`'s graph_parents as a Python list.

<h3 id="is_constant_jacobian"><code>is_constant_jacobian</code></h3>

Returns true iff the Jacobian is not a function of x.

Note: Jacobian is either constant for both forward and inverse or neither.

#### Returns:

* <b>`is_constant_jacobian`</b>: Python `bool`.

<h3 id="name"><code>name</code></h3>

Returns the string name of this `Bijector`.

<h3 id="skewness"><code>skewness</code></h3>

The `skewness` in: `Y  = Sinh((Arcsinh(X) + skewness) * tailweight)`.

<h3 id="tailweight"><code>tailweight</code></h3>

The `tailweight` in: `Y = Sinh((Arcsinh(X) + skewness) * tailweight)`.

<h3 id="validate_args"><code>validate_args</code></h3>

Returns True if Tensor arguments will be validated.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    skewness=0.0,
    tailweight=1.0,
    event_ndims=0,
    validate_args=False,
    name='sinh_arcsinh'
)
```

Instantiates the `SinhArcsinh` bijector.

#### Args:

* <b>`skewness`</b>:  Skewness parameter.  Float-type `Tensor`.
* <b>`tailweight`</b>:  Tailweight parameter.  Positive `Tensor` of same `dtype` as
    `skewness`
    and broadcastable `shape`.
* <b>`event_ndims`</b>: Python scalar indicating the number of dimensions associated
    with a particular draw from the distribution.
* <b>`validate_args`</b>: Python `bool` indicating whether arguments should be
    checked for correctness.
* <b>`name`</b>: Python `str` name given to ops managed by this object.

<h3 id="forward"><code>forward</code></h3>

``` python
forward(
    x,
    name='forward'
)
```

Returns the forward `Bijector` evaluation, i.e., X = g(Y).

#### Args:

* <b>`x`</b>: `Tensor`. The input to the "forward" evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

  `Tensor`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `x.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_forward` is not implemented.

<h3 id="forward_event_shape"><code>forward_event_shape</code></h3>

``` python
forward_event_shape(input_shape)
```

Shape of a single sample from a single batch as a `TensorShape`.

Same meaning as `forward_event_shape_tensor`. May be only partially defined.

#### Args:

* <b>`input_shape`</b>: `TensorShape` indicating event-portion shape passed into
    `forward` function.


#### Returns:

* <b>`forward_event_shape_tensor`</b>: `TensorShape` indicating event-portion shape
    after applying `forward`. Possibly unknown.

<h3 id="forward_event_shape_tensor"><code>forward_event_shape_tensor</code></h3>

``` python
forward_event_shape_tensor(
    input_shape,
    name='forward_event_shape_tensor'
)
```

Shape of a single sample from a single batch as an `int32` 1D `Tensor`.

#### Args:

* <b>`input_shape`</b>: `Tensor`, `int32` vector indicating event-portion shape
    passed into `forward` function.
* <b>`name`</b>: name to give to the op


#### Returns:

* <b>`forward_event_shape_tensor`</b>: `Tensor`, `int32` vector indicating
    event-portion shape after applying `forward`.

<h3 id="forward_log_det_jacobian"><code>forward_log_det_jacobian</code></h3>

``` python
forward_log_det_jacobian(
    x,
    name='forward_log_det_jacobian'
)
```

Returns both the forward_log_det_jacobian.

#### Args:

* <b>`x`</b>: `Tensor`. The input to the "forward" Jacobian evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

  `Tensor`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if neither `_forward_log_det_jacobian`
    nor {`_inverse`, `_inverse_log_det_jacobian`} are implemented.

<h3 id="inverse"><code>inverse</code></h3>

``` python
inverse(
    y,
    name='inverse'
)
```

Returns the inverse `Bijector` evaluation, i.e., X = g^{-1}(Y).

#### Args:

* <b>`y`</b>: `Tensor`. The input to the "inverse" evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

  `Tensor`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_inverse` is not implemented.

<h3 id="inverse_event_shape"><code>inverse_event_shape</code></h3>

``` python
inverse_event_shape(output_shape)
```

Shape of a single sample from a single batch as a `TensorShape`.

Same meaning as `inverse_event_shape_tensor`. May be only partially defined.

#### Args:

* <b>`output_shape`</b>: `TensorShape` indicating event-portion shape passed into
    `inverse` function.


#### Returns:

* <b>`inverse_event_shape_tensor`</b>: `TensorShape` indicating event-portion shape
    after applying `inverse`. Possibly unknown.

<h3 id="inverse_event_shape_tensor"><code>inverse_event_shape_tensor</code></h3>

``` python
inverse_event_shape_tensor(
    output_shape,
    name='inverse_event_shape_tensor'
)
```

Shape of a single sample from a single batch as an `int32` 1D `Tensor`.

#### Args:

* <b>`output_shape`</b>: `Tensor`, `int32` vector indicating event-portion shape
    passed into `inverse` function.
* <b>`name`</b>: name to give to the op


#### Returns:

* <b>`inverse_event_shape_tensor`</b>: `Tensor`, `int32` vector indicating
    event-portion shape after applying `inverse`.

<h3 id="inverse_log_det_jacobian"><code>inverse_log_det_jacobian</code></h3>

``` python
inverse_log_det_jacobian(
    y,
    name='inverse_log_det_jacobian'
)
```

Returns the (log o det o Jacobian o inverse)(y).

Mathematically, returns: `log(det(dX/dY))(Y)`. (Recall that: `X=g^{-1}(Y)`.)

Note that `forward_log_det_jacobian` is the negative of this function.

#### Args:

* <b>`y`</b>: `Tensor`. The input to the "inverse" Jacobian evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

  `Tensor`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_inverse_log_det_jacobian` is not implemented.



