<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.AdamOptimizer" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="apply_gradients"/>
<meta itemprop="property" content="compute_gradients"/>
<meta itemprop="property" content="get_name"/>
<meta itemprop="property" content="get_slot"/>
<meta itemprop="property" content="get_slot_names"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="GATE_GRAPH"/>
<meta itemprop="property" content="GATE_NONE"/>
<meta itemprop="property" content="GATE_OP"/>
</div>

# tf.train.AdamOptimizer

## Class `AdamOptimizer`

Inherits From: [`Optimizer`](../../tf/train/Optimizer.md)



Defined in [`tensorflow/python/training/adam.py`](https://www.tensorflow.org/code/tensorflow/python/training/adam.py).

See the guide: [Training > Optimizers](../../../../api_guides/python/train.md#Optimizers)

Optimizer that implements the Adam algorithm.

See [Kingma et al., 2014](http://arxiv.org/abs/1412.6980)
([pdf](http://arxiv.org/pdf/1412.6980.pdf)).

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    learning_rate=0.001,
    beta1=0.9,
    beta2=0.999,
    epsilon=1e-08,
    use_locking=False,
    name='Adam'
)
```

Construct a new Adam optimizer.

Initialization:

```
m_0 <- 0 (Initialize initial 1st moment vector)
v_0 <- 0 (Initialize initial 2nd moment vector)
t <- 0 (Initialize timestep)
```

The update rule for `variable` with gradient `g` uses an optimization
described at the end of section2 of the paper:

```
t <- t + 1
lr_t <- learning_rate * sqrt(1 - beta2^t) / (1 - beta1^t)

m_t <- beta1 * m_{t-1} + (1 - beta1) * g
v_t <- beta2 * v_{t-1} + (1 - beta2) * g * g
variable <- variable - lr_t * m_t / (sqrt(v_t) + epsilon)
```

The default value of 1e-8 for epsilon might not be a good default in
general. For example, when training an Inception network on ImageNet a
current good choice is 1.0 or 0.1. Note that since AdamOptimizer uses the
formulation just before Section 2.1 of the Kingma and Ba paper rather than
the formulation in Algorithm 1, the "epsilon" referred to here is "epsilon
hat" in the paper.

The sparse implementation of this algorithm (used when the gradient is an
IndexedSlices object, typically because of `tf.gather` or an embedding
lookup in the forward pass) does apply momentum to variable slices even if
they were not used in the forward pass (meaning they have a gradient equal
to zero). Momentum decay (beta1) is also applied to the entire momentum
accumulator. This means that the sparse behavior is equivalent to the dense
behavior (in contrast to some momentum implementations which ignore momentum
unless a variable slice was actually used).

#### Args:

* <b>`learning_rate`</b>: A Tensor or a floating point value.  The learning rate.
* <b>`beta1`</b>: A float value or a constant float tensor.
    The exponential decay rate for the 1st moment estimates.
* <b>`beta2`</b>: A float value or a constant float tensor.
    The exponential decay rate for the 2nd moment estimates.
* <b>`epsilon`</b>: A small constant for numerical stability. This epsilon is
    "epsilon hat" in the Kingma and Ba paper (in the formula just before
    Section 2.1), not the epsilon in Algorithm 1 of the paper.
* <b>`use_locking`</b>: If True use locks for update operations.
* <b>`name`</b>: Optional name for the operations created when applying gradients.
    Defaults to "Adam".

<h3 id="apply_gradients"><code>apply_gradients</code></h3>

``` python
apply_gradients(
    grads_and_vars,
    global_step=None,
    name=None
)
```

Apply gradients to variables.

This is the second part of `minimize()`. It returns an `Operation` that
applies gradients.

#### Args:

* <b>`grads_and_vars`</b>: List of (gradient, variable) pairs as returned by
    `compute_gradients()`.
* <b>`global_step`</b>: Optional `Variable` to increment by one after the
    variables have been updated.
* <b>`name`</b>: Optional name for the returned operation.  Default to the
    name passed to the `Optimizer` constructor.


#### Returns:

  An `Operation` that applies the specified gradients. If `global_step`
  was not None, that operation also increments `global_step`.


#### Raises:

* <b>`TypeError`</b>: If `grads_and_vars` is malformed.
* <b>`ValueError`</b>: If none of the variables have gradients.

<h3 id="compute_gradients"><code>compute_gradients</code></h3>

``` python
compute_gradients(
    loss,
    var_list=None,
    gate_gradients=GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    grad_loss=None
)
```

Compute gradients of `loss` for the variables in `var_list`.

This is the first part of `minimize()`.  It returns a list
of (gradient, variable) pairs where "gradient" is the gradient
for "variable".  Note that "gradient" can be a `Tensor`, an
`IndexedSlices`, or `None` if there is no gradient for the
given variable.

#### Args:

* <b>`loss`</b>: A Tensor containing the value to minimize.
* <b>`var_list`</b>: Optional list or tuple of `tf.Variable` to update to minimize
    `loss`.  Defaults to the list of variables collected in the graph
    under the key `GraphKey.TRAINABLE_VARIABLES`.
* <b>`gate_gradients`</b>: How to gate the computation of gradients.  Can be
    `GATE_NONE`, `GATE_OP`, or `GATE_GRAPH`.
* <b>`aggregation_method`</b>: Specifies the method used to combine gradient terms.
    Valid values are defined in the class `AggregationMethod`.
* <b>`colocate_gradients_with_ops`</b>: If True, try colocating gradients with
    the corresponding op.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.


#### Returns:

  A list of (gradient, variable) pairs. Variable is always present, but
  gradient can be `None`.


#### Raises:

* <b>`TypeError`</b>: If `var_list` contains anything else than `Variable` objects.
* <b>`ValueError`</b>: If some arguments are invalid.

<h3 id="get_name"><code>get_name</code></h3>

``` python
get_name()
```



<h3 id="get_slot"><code>get_slot</code></h3>

``` python
get_slot(
    var,
    name
)
```

Return a slot named `name` created for `var` by the Optimizer.

Some `Optimizer` subclasses use additional variables.  For example
`Momentum` and `Adagrad` use variables to accumulate updates.  This method
gives access to these `Variable` objects if for some reason you need them.

Use `get_slot_names()` to get the list of slot names created by the
`Optimizer`.

#### Args:

* <b>`var`</b>: A variable passed to `minimize()` or `apply_gradients()`.
* <b>`name`</b>: A string.


#### Returns:

  The `Variable` for the slot if it was created, `None` otherwise.

<h3 id="get_slot_names"><code>get_slot_names</code></h3>

``` python
get_slot_names()
```

Return a list of the names of slots created by the `Optimizer`.

See `get_slot()`.

#### Returns:

  A list of strings.

<h3 id="minimize"><code>minimize</code></h3>

``` python
minimize(
    loss,
    global_step=None,
    var_list=None,
    gate_gradients=GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    name=None,
    grad_loss=None
)
```

Add operations to minimize `loss` by updating `var_list`.

This method simply combines calls `compute_gradients()` and
`apply_gradients()`. If you want to process the gradient before applying
them call `compute_gradients()` and `apply_gradients()` explicitly instead
of using this function.

#### Args:

* <b>`loss`</b>: A `Tensor` containing the value to minimize.
* <b>`global_step`</b>: Optional `Variable` to increment by one after the
    variables have been updated.
* <b>`var_list`</b>: Optional list or tuple of `Variable` objects to update to
    minimize `loss`.  Defaults to the list of variables collected in
    the graph under the key `GraphKeys.TRAINABLE_VARIABLES`.
* <b>`gate_gradients`</b>: How to gate the computation of gradients.  Can be
    `GATE_NONE`, `GATE_OP`, or  `GATE_GRAPH`.
* <b>`aggregation_method`</b>: Specifies the method used to combine gradient terms.
    Valid values are defined in the class `AggregationMethod`.
* <b>`colocate_gradients_with_ops`</b>: If True, try colocating gradients with
    the corresponding op.
* <b>`name`</b>: Optional name for the returned operation.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.


#### Returns:

  An Operation that updates the variables in `var_list`.  If `global_step`
  was not `None`, that operation also increments `global_step`.


#### Raises:

* <b>`ValueError`</b>: If some of the variables are not `Variable` objects.



## Class Members

<h3 id="GATE_GRAPH"><code>GATE_GRAPH</code></h3>

<h3 id="GATE_NONE"><code>GATE_NONE</code></h3>

<h3 id="GATE_OP"><code>GATE_OP</code></h3>

