<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors" />
</div>

# Module: tf.contrib.distributions.bijectors



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/python/ops/bijectors/__init__.py).

Bijector Ops.


## Classes

[`class Affine`](../../../tf/contrib/distributions/bijectors/Affine.md): Compute `Y = g(X; shift, scale) = scale @ X + shift`.

[`class AffineLinearOperator`](../../../tf/contrib/distributions/bijectors/AffineLinearOperator.md): Compute `Y = g(X; shift, scale) = scale @ X + shift`.

[`class Bijector`](../../../tf/distributions/bijectors/Bijector.md): Interface for invertible transformations of a `Distribution` sample.

[`class Chain`](../../../tf/contrib/distributions/bijectors/Chain.md): Bijector which applies a sequence of bijectors.

[`class CholeskyOuterProduct`](../../../tf/contrib/distributions/bijectors/CholeskyOuterProduct.md): Compute `g(X) = X @ X.T`; X is lower-triangular, positive-diagonal matrix.

[`class ConditionalBijector`](../../../tf/contrib/distributions/bijectors/ConditionalBijector.md): Conditional Bijector is a Bijector that allows intrinsic conditioning.

[`class Exp`](../../../tf/contrib/distributions/bijectors/Exp.md): Compute `Y = g(X) = exp(X)`.

[`class Identity`](../../../tf/distributions/bijectors/Identity.md): Compute Y = g(X) = X.

[`class Inline`](../../../tf/contrib/distributions/bijectors/Inline.md): Bijector constructed from custom callables.

[`class Invert`](../../../tf/contrib/distributions/bijectors/Invert.md): Bijector which inverts another Bijector.

[`class PowerTransform`](../../../tf/contrib/distributions/bijectors/PowerTransform.md): Compute `Y = g(X) = (1 + X * c)**(1 / c), X >= -1 / c`.

[`class Sigmoid`](../../../tf/contrib/distributions/bijectors/Sigmoid.md): Bijector which computes `Y = g(X) = 1 / (1 + exp(-X))`.

[`class SigmoidCentered`](../../../tf/contrib/distributions/bijectors/SigmoidCentered.md): Bijector which computes Y = g(X) = exp([X 0]) / (1 + exp(-X)).

[`class SinhArcsinh`](../../../tf/contrib/distributions/bijectors/SinhArcsinh.md): Compute `Y = g(X) = Sinh( (Arcsinh(X) + skewness) * tailweight )`.

[`class SoftmaxCentered`](../../../tf/contrib/distributions/bijectors/SoftmaxCentered.md): Bijector which computes `Y = g(X) = exp([X 0]) / sum(exp([X 0]))`.

[`class Softplus`](../../../tf/contrib/distributions/bijectors/Softplus.md): Bijector which computes `Y = g(X) = Log[1 + exp(X)]`.

