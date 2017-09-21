<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.keras.preprocessing.text.text_to_word_sequence" />
</div>

# tf.contrib.keras.preprocessing.text.text_to_word_sequence

``` python
text_to_word_sequence(
    text,
    filters='!"#$%&()*+,-./:;<=>?@[\\]^_`{|}~\t\n',
    lower=True,
    split=' '
)
```



Defined in [`tensorflow/contrib/keras/python/keras/preprocessing/text.py`](https://www.tensorflow.org/code/tensorflow/contrib/keras/python/keras/preprocessing/text.py).

Converts a text to a sequence of words (or tokens).

#### Arguments:

    text: Input text (string).
    filters: Sequence of characters to filter out.
    lower: Whether to convert the input to lowercase.
    split: Sentence split marker (string).


#### Returns:

    A list of words (or tokens).