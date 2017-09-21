<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.backend.ctc_batch_cost" />
</div>

# tf.contrib.keras.backend.ctc_batch_cost

``` python
ctc_batch_cost(
    y_true,
    y_pred,
    input_length,
    label_length
)
```



Defined in [`tensorflow/contrib/keras/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/backend.py).

Runs CTC loss algorithm on each batch element.

#### Arguments:

    y_true: tensor `(samples, max_string_length)`
        containing the truth labels.
    y_pred: tensor `(samples, time_steps, num_categories)`
        containing the prediction, or output of the softmax.
    input_length: tensor `(samples, 1)` containing the sequence length for
        each batch item in `y_pred`.
    label_length: tensor `(samples, 1)` containing the sequence length for
        each batch item in `y_true`.


#### Returns:

    Tensor with shape (samples,1) containing the
        CTC loss of each element.