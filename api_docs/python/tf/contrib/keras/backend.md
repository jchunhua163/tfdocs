<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend" />
</div>

# Module: tf.contrib.keras.backend



Defined in [`tensorflow/contrib/keras/api/keras/backend/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/api/keras/backend/__init__.py).

Keras backend API.

## Functions

[`abs(...)`](../../../tf/contrib/keras/backend/abs.md): Element-wise absolute value.

[`all(...)`](../../../tf/contrib/keras/backend/all.md): Bitwise reduction (logical AND).

[`any(...)`](../../../tf/contrib/keras/backend/any.md): Bitwise reduction (logical OR).

[`arange(...)`](../../../tf/contrib/keras/backend/arange.md): Creates a 1D tensor containing a sequence of integers.

[`argmax(...)`](../../../tf/contrib/keras/backend/argmax.md): Returns the index of the maximum value along an axis.

[`argmin(...)`](../../../tf/contrib/keras/backend/argmin.md): Returns the index of the minimum value along an axis.

[`backend(...)`](../../../tf/contrib/keras/backend/backend.md): Publicly accessible method for determining the current backend.

[`batch_dot(...)`](../../../tf/contrib/keras/backend/batch_dot.md): Batchwise dot product.

[`batch_flatten(...)`](../../../tf/contrib/keras/backend/batch_flatten.md): Turn a nD tensor into a 2D tensor with same 0th dimension.

[`batch_get_value(...)`](../../../tf/contrib/keras/backend/batch_get_value.md): Returns the value of more than one tensor variable.

[`batch_normalization(...)`](../../../tf/contrib/keras/backend/batch_normalization.md): Applies batch normalization on x given mean, var, beta and gamma.

[`batch_set_value(...)`](../../../tf/contrib/keras/backend/batch_set_value.md): Sets the values of many tensor variables at once.

[`bias_add(...)`](../../../tf/contrib/keras/backend/bias_add.md): Adds a bias vector to a tensor.

[`binary_crossentropy(...)`](../../../tf/contrib/keras/backend/binary_crossentropy.md): Binary crossentropy between an output tensor and a target tensor.

[`cast(...)`](../../../tf/contrib/keras/backend/cast.md): Casts a tensor to a different dtype and returns it.

[`cast_to_floatx(...)`](../../../tf/contrib/keras/backend/cast_to_floatx.md): Cast a Numpy array to the default Keras float type.

[`categorical_crossentropy(...)`](../../../tf/contrib/keras/backend/categorical_crossentropy.md): Categorical crossentropy between an output tensor and a target tensor.

[`clear_session(...)`](../../../tf/contrib/keras/backend/clear_session.md): Destroys the current TF graph and creates a new one.

[`clip(...)`](../../../tf/contrib/keras/backend/clip.md): Element-wise value clipping.

[`concatenate(...)`](../../../tf/contrib/keras/backend/concatenate.md): Concatenates a list of tensors alongside the specified axis.

[`constant(...)`](../../../tf/contrib/keras/backend/constant.md): Creates a constant tensor.

[`conv1d(...)`](../../../tf/contrib/keras/backend/conv1d.md): 1D convolution.

[`conv2d(...)`](../../../tf/contrib/keras/backend/conv2d.md): 2D convolution.

[`conv2d_transpose(...)`](../../../tf/contrib/keras/backend/conv2d_transpose.md): 2D deconvolution (i.e.

[`conv3d(...)`](../../../tf/contrib/keras/backend/conv3d.md): 3D convolution.

[`cos(...)`](../../../tf/contrib/keras/backend/cos.md): Computes cos of x element-wise.

[`count_params(...)`](../../../tf/contrib/keras/backend/count_params.md): Returns the number of scalars in a Keras variable.

[`ctc_batch_cost(...)`](../../../tf/contrib/keras/backend/ctc_batch_cost.md): Runs CTC loss algorithm on each batch element.

[`ctc_decode(...)`](../../../tf/contrib/keras/backend/ctc_decode.md): Decodes the output of a softmax.

[`ctc_label_dense_to_sparse(...)`](../../../tf/contrib/keras/backend/ctc_label_dense_to_sparse.md): Converts CTC labels from dense to sparse.

[`dot(...)`](../../../tf/contrib/keras/backend/dot.md): Multiplies 2 tensors (and/or variables) and returns a *tensor*.

[`dropout(...)`](../../../tf/contrib/keras/backend/dropout.md): Sets entries in `x` to zero at random, while scaling the entire tensor.

[`dtype(...)`](../../../tf/contrib/keras/backend/dtype.md): Returns the dtype of a Keras tensor or variable, as a string.

[`elu(...)`](../../../tf/contrib/keras/backend/elu.md): Exponential linear unit.

[`epsilon(...)`](../../../tf/contrib/keras/backend/epsilon.md): Returns the value of the fuzz factor used in numeric expressions.

[`equal(...)`](../../../tf/contrib/keras/backend/equal.md): Element-wise equality between two tensors.

[`eval(...)`](../../../tf/contrib/keras/backend/eval.md): Evaluates the value of a variable.

[`exp(...)`](../../../tf/contrib/keras/backend/exp.md): Element-wise exponential.

[`expand_dims(...)`](../../../tf/contrib/keras/backend/expand_dims.md): Adds a 1-sized dimension at index "axis".

[`eye(...)`](../../../tf/contrib/keras/backend/eye.md): Instantiate an identity matrix and returns it.

[`flatten(...)`](../../../tf/contrib/keras/backend/flatten.md): Flatten a tensor.

[`floatx(...)`](../../../tf/contrib/keras/backend/floatx.md): Returns the default float type, as a string.

[`foldl(...)`](../../../tf/contrib/keras/backend/foldl.md): Reduce elems using fn to combine them from left to right.

[`foldr(...)`](../../../tf/contrib/keras/backend/foldr.md): Reduce elems using fn to combine them from right to left.

[`function(...)`](../../../tf/contrib/keras/backend/function.md): Instantiates a Keras function.

[`gather(...)`](../../../tf/contrib/keras/backend/gather.md): Retrieves the elements of indices `indices` in the tensor `reference`.

[`get_session(...)`](../../../tf/contrib/keras/backend/get_session.md): Returns the TF session to be used by the backend.

[`get_uid(...)`](../../../tf/contrib/keras/backend/get_uid.md): Associates a string prefix with an integer counter in a TensorFlow graph.

[`get_value(...)`](../../../tf/contrib/keras/backend/get_value.md): Returns the value of a variable.

[`gradients(...)`](../../../tf/contrib/keras/backend/gradients.md): Returns the gradients of `variables` w.r.t. `loss`.

[`greater(...)`](../../../tf/contrib/keras/backend/greater.md): Element-wise truth value of (x > y).

[`greater_equal(...)`](../../../tf/contrib/keras/backend/greater_equal.md): Element-wise truth value of (x >= y).

[`hard_sigmoid(...)`](../../../tf/contrib/keras/backend/hard_sigmoid.md): Segment-wise linear approximation of sigmoid.

[`image_data_format(...)`](../../../tf/contrib/keras/backend/image_data_format.md): Returns the default image data format convention.

[`in_test_phase(...)`](../../../tf/contrib/keras/backend/in_test_phase.md): Selects `x` in test phase, and `alt` otherwise.

[`in_top_k(...)`](../../../tf/contrib/keras/backend/in_top_k.md): Returns whether the `targets` are in the top `k` `predictions`.

[`in_train_phase(...)`](../../../tf/contrib/keras/backend/in_train_phase.md): Selects `x` in train phase, and `alt` otherwise.

[`int_shape(...)`](../../../tf/contrib/keras/backend/int_shape.md): Returns the shape tensor or variable as a tuple of int or None entries.

[`is_sparse(...)`](../../../tf/contrib/keras/backend/is_sparse.md): Returns whether a tensor is a sparse tensor.

[`l2_normalize(...)`](../../../tf/contrib/keras/backend/l2_normalize.md): Normalizes a tensor wrt the L2 norm alongside the specified axis.

[`learning_phase(...)`](../../../tf/contrib/keras/backend/learning_phase.md): Returns the learning phase flag.

[`less(...)`](../../../tf/contrib/keras/backend/less.md): Element-wise truth value of (x < y).

[`less_equal(...)`](../../../tf/contrib/keras/backend/less_equal.md): Element-wise truth value of (x <= y).

[`log(...)`](../../../tf/contrib/keras/backend/log.md): Element-wise log.

[`manual_variable_initialization(...)`](../../../tf/contrib/keras/backend/manual_variable_initialization.md): Sets the manual variable initialization flag.

[`map_fn(...)`](../../../tf/contrib/keras/backend/map_fn.md): Map the function fn over the elements elems and return the outputs.

[`max(...)`](../../../tf/contrib/keras/backend/max.md): Maximum value in a tensor.

[`maximum(...)`](../../../tf/contrib/keras/backend/maximum.md): Element-wise maximum of two tensors.

[`mean(...)`](../../../tf/contrib/keras/backend/mean.md): Mean of a tensor, alongside the specified axis.

[`min(...)`](../../../tf/contrib/keras/backend/min.md): Minimum value in a tensor.

[`minimum(...)`](../../../tf/contrib/keras/backend/minimum.md): Element-wise minimum of two tensors.

[`moving_average_update(...)`](../../../tf/contrib/keras/backend/moving_average_update.md): Compute the moving average of a variable.

[`name_scope(...)`](../../../tf/name_scope.md): Returns a context manager for use when defining a Python op.

[`ndim(...)`](../../../tf/contrib/keras/backend/ndim.md): Returns the number of axes in a tensor, as an integer.

[`normalize_batch_in_training(...)`](../../../tf/contrib/keras/backend/normalize_batch_in_training.md): Computes mean and std for batch then apply batch_normalization on batch.

[`not_equal(...)`](../../../tf/contrib/keras/backend/not_equal.md): Element-wise inequality between two tensors.

[`one_hot(...)`](../../../tf/contrib/keras/backend/one_hot.md): Computes the one-hot representation of an integer tensor.

[`ones(...)`](../../../tf/contrib/keras/backend/ones.md): Instantiates an all-ones tensor variable and returns it.

[`ones_like(...)`](../../../tf/contrib/keras/backend/ones_like.md): Instantiates an all-ones variable of the same shape as another tensor.

[`permute_dimensions(...)`](../../../tf/contrib/keras/backend/permute_dimensions.md): Permutes axes in a tensor.

[`placeholder(...)`](../../../tf/contrib/keras/backend/placeholder.md): Instantiates a placeholder tensor and returns it.

[`pool2d(...)`](../../../tf/contrib/keras/backend/pool2d.md): 2D Pooling.

[`pool3d(...)`](../../../tf/contrib/keras/backend/pool3d.md): 3D Pooling.

[`pow(...)`](../../../tf/contrib/keras/backend/pow.md): Element-wise exponentiation.

[`print_tensor(...)`](../../../tf/contrib/keras/backend/print_tensor.md): Prints `message` and the tensor value when evaluated.

[`prod(...)`](../../../tf/contrib/keras/backend/prod.md): Multiplies the values in a tensor, alongside the specified axis.

[`random_binomial(...)`](../../../tf/contrib/keras/backend/random_binomial.md): Returns a tensor with random binomial distribution of values.

[`random_normal(...)`](../../../tf/contrib/keras/backend/random_normal.md): Returns a tensor with normal distribution of values.

[`random_normal_variable(...)`](../../../tf/contrib/keras/backend/random_normal_variable.md): Instantiates a variable with values drawn from a normal distribution.

[`random_uniform(...)`](../../../tf/contrib/keras/backend/random_uniform.md): Returns a tensor with uniform distribution of values.

[`random_uniform_variable(...)`](../../../tf/contrib/keras/backend/random_uniform_variable.md): Instantiates a variable with values drawn from a uniform distribution.

[`relu(...)`](../../../tf/contrib/keras/backend/relu.md): Rectified linear unit.

[`repeat(...)`](../../../tf/contrib/keras/backend/repeat.md): Repeats a 2D tensor.

[`repeat_elements(...)`](../../../tf/contrib/keras/backend/repeat_elements.md): Repeats the elements of a tensor along an axis, like `np.repeat`.

[`reset_uids(...)`](../../../tf/contrib/keras/backend/reset_uids.md)

[`reshape(...)`](../../../tf/contrib/keras/backend/reshape.md): Reshapes a tensor to the specified shape.

[`resize_images(...)`](../../../tf/contrib/keras/backend/resize_images.md): Resizes the images contained in a 4D tensor.

[`resize_volumes(...)`](../../../tf/contrib/keras/backend/resize_volumes.md): Resizes the volume contained in a 5D tensor.

[`reverse(...)`](../../../tf/contrib/keras/backend/reverse.md): Reverse a tensor along the specified axes.

[`rnn(...)`](../../../tf/contrib/keras/backend/rnn.md): Iterates over the time dimension of a tensor.

[`round(...)`](../../../tf/contrib/keras/backend/round.md): Element-wise rounding to the closest integer.

[`separable_conv2d(...)`](../../../tf/contrib/keras/backend/separable_conv2d.md): 2D convolution with separable filters.

[`set_epsilon(...)`](../../../tf/contrib/keras/backend/set_epsilon.md): Sets the value of the fuzz factor used in numeric expressions.

[`set_floatx(...)`](../../../tf/contrib/keras/backend/set_floatx.md): Sets the default float type.

[`set_image_data_format(...)`](../../../tf/contrib/keras/backend/set_image_data_format.md): Sets the value of the image data format convention.

[`set_learning_phase(...)`](../../../tf/contrib/keras/backend/set_learning_phase.md): Sets the learning phase to a fixed value.

[`set_session(...)`](../../../tf/contrib/keras/backend/set_session.md): Sets the global TensorFlow session.

[`set_value(...)`](../../../tf/contrib/keras/backend/set_value.md): Sets the value of a variable, from a Numpy array.

[`shape(...)`](../../../tf/contrib/keras/backend/shape.md): Returns the symbolic shape of a tensor or variable.

[`sigmoid(...)`](../../../tf/contrib/keras/backend/sigmoid.md): Element-wise sigmoid.

[`sign(...)`](../../../tf/contrib/keras/backend/sign.md): Element-wise sign.

[`sin(...)`](../../../tf/contrib/keras/backend/sin.md): Computes sin of x element-wise.

[`softmax(...)`](../../../tf/contrib/keras/backend/softmax.md): Softmax of a tensor.

[`softplus(...)`](../../../tf/contrib/keras/backend/softplus.md): Softplus of a tensor.

[`softsign(...)`](../../../tf/contrib/keras/backend/softsign.md): Softsign of a tensor.

[`sparse_categorical_crossentropy(...)`](../../../tf/contrib/keras/backend/sparse_categorical_crossentropy.md): Categorical crossentropy with integer targets.

[`spatial_2d_padding(...)`](../../../tf/contrib/keras/backend/spatial_2d_padding.md): Pads the 2nd and 3rd dimensions of a 4D tensor.

[`spatial_3d_padding(...)`](../../../tf/contrib/keras/backend/spatial_3d_padding.md): Pads 5D tensor with zeros along the depth, height, width dimensions.

[`sqrt(...)`](../../../tf/contrib/keras/backend/sqrt.md): Element-wise square root.

[`square(...)`](../../../tf/contrib/keras/backend/square.md): Element-wise square.

[`squeeze(...)`](../../../tf/contrib/keras/backend/squeeze.md): Removes a 1-dimension from the tensor at index "axis".

[`stack(...)`](../../../tf/contrib/keras/backend/stack.md): Stacks a list of rank `R` tensors into a rank `R+1` tensor.

[`std(...)`](../../../tf/contrib/keras/backend/std.md): Standard deviation of a tensor, alongside the specified axis.

[`stop_gradient(...)`](../../../tf/contrib/keras/backend/stop_gradient.md): Returns `variables` but with zero gradient w.r.t. every other variable.

[`sum(...)`](../../../tf/contrib/keras/backend/sum.md): Sum of the values in a tensor, alongside the specified axis.

[`switch(...)`](../../../tf/contrib/keras/backend/switch.md): Switches between two operations depending on a scalar value.

[`tanh(...)`](../../../tf/contrib/keras/backend/tanh.md): Element-wise tanh.

[`temporal_padding(...)`](../../../tf/contrib/keras/backend/temporal_padding.md): Pads the middle dimension of a 3D tensor.

[`to_dense(...)`](../../../tf/contrib/keras/backend/to_dense.md): Converts a sparse tensor into a dense tensor and returns it.

[`transpose(...)`](../../../tf/contrib/keras/backend/transpose.md): Transposes a tensor and returns it.

[`truncated_normal(...)`](../../../tf/contrib/keras/backend/truncated_normal.md): Returns a tensor with truncated random normal distribution of values.

[`update(...)`](../../../tf/contrib/keras/backend/update.md)

[`update_add(...)`](../../../tf/contrib/keras/backend/update_add.md): Update the value of `x` by adding `increment`.

[`update_sub(...)`](../../../tf/contrib/keras/backend/update_sub.md): Update the value of `x` by subtracting `decrement`.

[`var(...)`](../../../tf/contrib/keras/backend/var.md): Variance of a tensor, alongside the specified axis.

[`variable(...)`](../../../tf/contrib/keras/backend/variable.md): Instantiates a variable and returns it.

[`zeros(...)`](../../../tf/contrib/keras/backend/zeros.md): Instantiates an all-zeros variable and returns it.

[`zeros_like(...)`](../../../tf/contrib/keras/backend/zeros_like.md): Instantiates an all-zeros variable of the same shape as another tensor.

