<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.layers" />
</div>

# Module: tf.contrib.keras.layers



Defined in [`tensorflow/contrib/keras/api/keras/layers/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/api/keras/layers/__init__.py).

Keras layers API.

## Classes

[`class Activation`](../../../tf/contrib/keras/layers/Activation.md): Applies an activation function to an output.

[`class ActivityRegularization`](../../../tf/contrib/keras/layers/ActivityRegularization.md): Layer that applies an update to the cost function based input activity.

[`class Add`](../../../tf/contrib/keras/layers/Add.md): Layer that adds a list of inputs.

[`class Average`](../../../tf/contrib/keras/layers/Average.md): Layer that averages a list of inputs.

[`class AveragePooling1D`](../../../tf/contrib/keras/layers/AveragePooling1D.md): Average pooling for temporal data.

[`class AveragePooling2D`](../../../tf/contrib/keras/layers/AveragePooling2D.md): Average pooling operation for spatial data.

[`class AveragePooling3D`](../../../tf/contrib/keras/layers/AveragePooling3D.md): Average pooling operation for 3D data (spatial or spatio-temporal).

[`class AvgPool1D`](../../../tf/contrib/keras/layers/AveragePooling1D.md): Average pooling for temporal data.

[`class AvgPool2D`](../../../tf/contrib/keras/layers/AveragePooling2D.md): Average pooling operation for spatial data.

[`class AvgPool3D`](../../../tf/contrib/keras/layers/AveragePooling3D.md): Average pooling operation for 3D data (spatial or spatio-temporal).

[`class BatchNormalization`](../../../tf/contrib/keras/layers/BatchNormalization.md): Batch normalization layer (Ioffe and Szegedy, 2014).

[`class Bidirectional`](../../../tf/contrib/keras/layers/Bidirectional.md): Bidirectional wrapper for RNNs.

[`class Concatenate`](../../../tf/contrib/keras/layers/Concatenate.md): Layer that concatenates a list of inputs.

[`class Conv1D`](../../../tf/contrib/keras/layers/Conv1D.md): 1D convolution layer (e.g. temporal convolution).

[`class Conv2D`](../../../tf/contrib/keras/layers/Conv2D.md): 2D convolution layer (e.g. spatial convolution over images).

[`class Conv2DTranspose`](../../../tf/contrib/keras/layers/Conv2DTranspose.md): Transposed convolution layer (sometimes called Deconvolution).

[`class Conv3D`](../../../tf/contrib/keras/layers/Conv3D.md): 3D convolution layer (e.g. spatial convolution over volumes).

[`class ConvLSTM2D`](../../../tf/contrib/keras/layers/ConvLSTM2D.md): Convolutional LSTM.

[`class Convolution1D`](../../../tf/contrib/keras/layers/Conv1D.md): 1D convolution layer (e.g. temporal convolution).

[`class Convolution2D`](../../../tf/contrib/keras/layers/Conv2D.md): 2D convolution layer (e.g. spatial convolution over images).

[`class Convolution2DTranspose`](../../../tf/contrib/keras/layers/Conv2DTranspose.md): Transposed convolution layer (sometimes called Deconvolution).

[`class Convolution3D`](../../../tf/contrib/keras/layers/Conv3D.md): 3D convolution layer (e.g. spatial convolution over volumes).

[`class Cropping1D`](../../../tf/contrib/keras/layers/Cropping1D.md): Cropping layer for 1D input (e.g. temporal sequence).

[`class Cropping2D`](../../../tf/contrib/keras/layers/Cropping2D.md): Cropping layer for 2D input (e.g. picture).

[`class Cropping3D`](../../../tf/contrib/keras/layers/Cropping3D.md): Cropping layer for 3D data (e.g.

[`class Dense`](../../../tf/contrib/keras/layers/Dense.md): Just your regular densely-connected NN layer.

[`class Dot`](../../../tf/contrib/keras/layers/Dot.md): Layer that computes a dot product between samples in two tensors.

[`class Dropout`](../../../tf/contrib/keras/layers/Dropout.md): Applies Dropout to the input.

[`class ELU`](../../../tf/contrib/keras/layers/ELU.md): Exponential Linear Unit.

[`class Embedding`](../../../tf/contrib/keras/layers/Embedding.md): Turns positive integers (indexes) into dense vectors of fixed size.

[`class Flatten`](../../../tf/contrib/keras/layers/Flatten.md): Flattens the input. Does not affect the batch size.

[`class GRU`](../../../tf/contrib/keras/layers/GRU.md): Gated Recurrent Unit - Cho et al.

[`class GaussianDropout`](../../../tf/contrib/keras/layers/GaussianDropout.md): Apply multiplicative 1-centered Gaussian noise.

[`class GaussianNoise`](../../../tf/contrib/keras/layers/GaussianNoise.md): Apply additive zero-centered Gaussian noise.

[`class GlobalAveragePooling1D`](../../../tf/contrib/keras/layers/GlobalAveragePooling1D.md): Global average pooling operation for temporal data.

[`class GlobalAveragePooling2D`](../../../tf/contrib/keras/layers/GlobalAveragePooling2D.md): Global average pooling operation for spatial data.

[`class GlobalAveragePooling3D`](../../../tf/contrib/keras/layers/GlobalAveragePooling3D.md): Global Average pooling operation for 3D data.

[`class GlobalAvgPool1D`](../../../tf/contrib/keras/layers/GlobalAveragePooling1D.md): Global average pooling operation for temporal data.

[`class GlobalAvgPool2D`](../../../tf/contrib/keras/layers/GlobalAveragePooling2D.md): Global average pooling operation for spatial data.

[`class GlobalAvgPool3D`](../../../tf/contrib/keras/layers/GlobalAveragePooling3D.md): Global Average pooling operation for 3D data.

[`class GlobalMaxPool1D`](../../../tf/contrib/keras/layers/GlobalMaxPool1D.md): Global max pooling operation for temporal data.

[`class GlobalMaxPool2D`](../../../tf/contrib/keras/layers/GlobalMaxPool2D.md): Global max pooling operation for spatial data.

[`class GlobalMaxPool3D`](../../../tf/contrib/keras/layers/GlobalMaxPool3D.md): Global Max pooling operation for 3D data.

[`class GlobalMaxPooling1D`](../../../tf/contrib/keras/layers/GlobalMaxPool1D.md): Global max pooling operation for temporal data.

[`class GlobalMaxPooling2D`](../../../tf/contrib/keras/layers/GlobalMaxPool2D.md): Global max pooling operation for spatial data.

[`class GlobalMaxPooling3D`](../../../tf/contrib/keras/layers/GlobalMaxPool3D.md): Global Max pooling operation for 3D data.

[`class InputLayer`](../../../tf/contrib/keras/layers/InputLayer.md): Layer to be used as an entry point into a graph.

[`class InputSpec`](../../../tf/contrib/keras/layers/InputSpec.md): Specifies the ndim, dtype and shape of every input to a layer.

[`class LSTM`](../../../tf/contrib/keras/layers/LSTM.md): Long-Short Term Memory unit - Hochreiter 1997.

[`class Lambda`](../../../tf/contrib/keras/layers/Lambda.md): Wraps arbitrary expression as a `Layer` object.

[`class Layer`](../../../tf/contrib/keras/layers/Layer.md): Abstract base layer class.

[`class LeakyReLU`](../../../tf/contrib/keras/layers/LeakyReLU.md): Leaky version of a Rectified Linear Unit.

[`class LocallyConnected1D`](../../../tf/contrib/keras/layers/LocallyConnected1D.md): Locally-connected layer for 1D inputs.

[`class LocallyConnected2D`](../../../tf/contrib/keras/layers/LocallyConnected2D.md): Locally-connected layer for 2D inputs.

[`class Masking`](../../../tf/contrib/keras/layers/Masking.md): Masks a sequence by using a mask value to skip timesteps.

[`class MaxPool1D`](../../../tf/contrib/keras/layers/MaxPool1D.md): Max pooling operation for temporal data.

[`class MaxPool2D`](../../../tf/contrib/keras/layers/MaxPool2D.md): Max pooling operation for spatial data.

[`class MaxPool3D`](../../../tf/contrib/keras/layers/MaxPool3D.md): Max pooling operation for 3D data (spatial or spatio-temporal).

[`class MaxPooling1D`](../../../tf/contrib/keras/layers/MaxPool1D.md): Max pooling operation for temporal data.

[`class MaxPooling2D`](../../../tf/contrib/keras/layers/MaxPool2D.md): Max pooling operation for spatial data.

[`class MaxPooling3D`](../../../tf/contrib/keras/layers/MaxPool3D.md): Max pooling operation for 3D data (spatial or spatio-temporal).

[`class Maximum`](../../../tf/contrib/keras/layers/Maximum.md): Layer that computes the maximum (element-wise) a list of inputs.

[`class Multiply`](../../../tf/contrib/keras/layers/Multiply.md): Layer that multiplies (element-wise) a list of inputs.

[`class PReLU`](../../../tf/contrib/keras/layers/PReLU.md): Parametric Rectified Linear Unit.

[`class Permute`](../../../tf/contrib/keras/layers/Permute.md): Permutes the dimensions of the input according to a given pattern.

[`class RepeatVector`](../../../tf/contrib/keras/layers/RepeatVector.md): Repeats the input n times.

[`class Reshape`](../../../tf/contrib/keras/layers/Reshape.md): Reshapes an output to a certain shape.

[`class SeparableConv2D`](../../../tf/contrib/keras/layers/SeparableConv2D.md): Depthwise separable 2D convolution.

[`class SeparableConvolution2D`](../../../tf/contrib/keras/layers/SeparableConv2D.md): Depthwise separable 2D convolution.

[`class SimpleRNN`](../../../tf/contrib/keras/layers/SimpleRNN.md): Fully-connected RNN where the output is to be fed back to input.

[`class SpatialDropout1D`](../../../tf/contrib/keras/layers/SpatialDropout1D.md): Spatial 1D version of Dropout.

[`class SpatialDropout2D`](../../../tf/contrib/keras/layers/SpatialDropout2D.md): Spatial 2D version of Dropout.

[`class SpatialDropout3D`](../../../tf/contrib/keras/layers/SpatialDropout3D.md): Spatial 3D version of Dropout.

[`class ThresholdedReLU`](../../../tf/contrib/keras/layers/ThresholdedReLU.md): Thresholded Rectified Linear Unit.

[`class TimeDistributed`](../../../tf/contrib/keras/layers/TimeDistributed.md): This wrapper allows to apply a layer to every temporal slice of an input.

[`class UpSampling1D`](../../../tf/contrib/keras/layers/UpSampling1D.md): Upsampling layer for 1D inputs.

[`class UpSampling2D`](../../../tf/contrib/keras/layers/UpSampling2D.md): Upsampling layer for 2D inputs.

[`class UpSampling3D`](../../../tf/contrib/keras/layers/UpSampling3D.md): Upsampling layer for 3D inputs.

[`class Wrapper`](../../../tf/contrib/keras/layers/Wrapper.md): Abstract wrapper base class.

[`class ZeroPadding1D`](../../../tf/contrib/keras/layers/ZeroPadding1D.md): Zero-padding layer for 1D input (e.g. temporal sequence).

[`class ZeroPadding2D`](../../../tf/contrib/keras/layers/ZeroPadding2D.md): Zero-padding layer for 2D input (e.g. picture).

[`class ZeroPadding3D`](../../../tf/contrib/keras/layers/ZeroPadding3D.md): Zero-padding layer for 3D data (spatial or spatio-temporal).

## Functions

[`Input(...)`](../../../tf/contrib/keras/layers/Input.md): `Input()` is used to instantiate a Keras tensor.

[`add(...)`](../../../tf/contrib/keras/layers/add.md): Functional interface to the `Add` layer.

[`average(...)`](../../../tf/contrib/keras/layers/average.md): Functional interface to the `Average` layer.

[`concatenate(...)`](../../../tf/contrib/keras/layers/concatenate.md): Functional interface to the `Concatenate` layer.

[`dot(...)`](../../../tf/contrib/keras/layers/dot.md): Functional interface to the `Dot` layer.

[`maximum(...)`](../../../tf/contrib/keras/layers/maximum.md): Functional interface to the `Maximum` layer.

[`multiply(...)`](../../../tf/contrib/keras/layers/multiply.md): Functional interface to the `Multiply` layer.

