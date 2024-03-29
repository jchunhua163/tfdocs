<!-- DO NOT EDIT! Automatically generated file. -->
# TensorFlow Linear Model Tutorial

In this tutorial, we will use the tf.estimator API in TensorFlow to solve a
binary classification problem: Given census data about a person such as age,
gender, education and occupation (the features), we will try to predict whether
or not the person earns more than 50,000 dollars a year (the target label). We
will train a **logistic regression** model, and given an individual's
information our model will output a number between 0 and 1, which can be
interpreted as the probability that the individual has an annual income of over
50,000 dollars.

## Setup

To try the code for this tutorial:

1.  [Install TensorFlow](../install/index.md) if you haven't already.

2.  Download [the tutorial code](https://www.tensorflow.org/code/tensorflow/examples/learn/wide_n_deep_tutorial.py).

3.  Install the pandas data analysis library. tf.estimator doesn't require pandas, but it does support it, and this tutorial uses pandas. To install pandas:

    a. Get `pip`:

        # Ubuntu/Linux 64-bit
        $ sudo apt-get install python-pip python-dev

        # Mac OS X
        $ sudo easy_install pip
        $ sudo easy_install --upgrade six

    b. Use `pip` to install pandas:

        $ sudo pip install pandas

    If you have trouble installing pandas, consult the
    [instructions](http://pandas.pydata.org/pandas-docs/stable/install.html)
    on the pandas site.

4. Execute the tutorial code with the following command to train the linear
model described in this tutorial:

        $ python wide_n_deep_tutorial.py --model_type=wide

Read on to find out how this code builds its linear model.

## Reading The Census Data

The dataset we'll be using is the
[Census Income Dataset](https://archive.ics.uci.edu/ml/datasets/Census+Income).
You can download the
[training data](https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data)
and [test data](https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.test)
manually or use code like this:

```python
import tempfile
import urllib
train_file = tempfile.NamedTemporaryFile()
test_file = tempfile.NamedTemporaryFile()
urllib.urlretrieve("https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data", train_file.name)
urllib.urlretrieve("https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.test", test_file.name)
```

Once the CSV files are downloaded, let's read them into
[Pandas](http://pandas.pydata.org/) dataframes.

```python
import pandas as pd
CSV_COLUMNS = [
    "age", "workclass", "fnlwgt", "education", "education_num",
    "marital_status", "occupation", "relationship", "race", "gender",
    "capital_gain", "capital_loss", "hours_per_week", "native_country",
    "income_bracket"]
df_train = pd.read_csv(train_file.name, names=CSV_COLUMNS, skipinitialspace=True)
df_test = pd.read_csv(test_file.name, names=CSV_COLUMNS, skipinitialspace=True, skiprows=1)
```

Since the task is a binary classification problem, we'll construct a label
column named "label" whose value is 1 if the income is over 50K, and 0
otherwise.

```python
train_labels = (df_train["income_bracket"].apply(lambda x: ">50K" in x)).astype(int)
test_labels = (df_test["income_bracket"].apply(lambda x: ">50K" in x)).astype(int)
```

Next, let's take a look at the dataframe and see which columns we can use to
predict the target label. The columns can be grouped into two types—categorical
and continuous columns:

*   A column is called **categorical** if its value can only be one of the
    categories in a finite set. For example, the native country of a person
    (U.S., India, Japan, etc.) or the education level (high school, college,
    etc.) are categorical columns.
*   A column is called **continuous** if its value can be any numerical value in
    a continuous range. For example, the capital gain of a person (e.g. $14,084)
    is a continuous column.

Here's a list of columns available in the Census Income dataset:

| Column Name    | Type        | Description                       | {.sortable}
| -------------- | ----------- | --------------------------------- |
| age            | Continuous  | The age of the individual         |
| workclass      | Categorical | The type of employer the          |
:                :             : individual has (government,       :
:                :             : military, private, etc.).         :
| fnlwgt         | Continuous  | The number of people the census   |
:                :             : takers believe that observation   :
:                :             : represents (sample weight). This  :
:                :             : variable will not be used.        :
| education      | Categorical | The highest level of education    |
:                :             : achieved for that individual.     :
| education_num  | Continuous  | The highest level of education in |
:                :             : numerical form.                   :
| marital_status | Categorical | Marital status of the individual. |
| occupation     | Categorical | The occupation of the individual. |
| relationship   | Categorical | Wife, Own-child, Husband,         |
:                :             : Not-in-family, Other-relative,    :
:                :             : Unmarried.                        :
| race           | Categorical | White, Asian-Pac-Islander,        |
:                :             : Amer-Indian-Eskimo, Other, Black. :
| gender         | Categorical | Female, Male.                     |
| capital_gain   | Continuous  | Capital gains recorded.           |
| capital_loss   | Continuous  | Capital Losses recorded.          |
| hours_per_week | Continuous  | Hours worked per week.            |
| native_country | Categorical | Country of origin of the          |
:                :             : individual.                       :
| income         | Categorical | ">50K" or "<=50K", meaning        |
:                :             : whether the person makes more     :
:                :             : than \$50,000 annually.           :

## Converting Data into Tensors

When building a tf.estimator model, the input data is specified by means of an
Input Builder function. This builder function will not be called until it is
later passed to tf.estimator.Estimator methods such as `train` and `evaluate`.
The purpose of this function is to construct the input data, which is
represented in the form of [`tf.Tensor`](../api_docs/python/tf/Tensor.md)s or [`tf.SparseTensor`](../api_docs/python/tf/SparseTensor.md)s.
In more detail, the Input Builder function returns the following as a pair:

1.  `feature_cols`: A dict from feature column names to `Tensors` or
    `SparseTensors`.
2.  `label`: A `Tensor` containing the label column.

The keys of the `feature_cols` will be used to construct columns in the
next section. Because we want to call the `train` and `evaluate` methods with
different data, we define a method that returns an input function based on the
given data. Note that the returned input function will be called while
constructing the TensorFlow graph, not while running the graph. What it is
returning is a representation of the input data as the fundamental unit of
TensorFlow computations, a `Tensor` (or `SparseTensor`).

We use the `tf.estimator.inputs.pandas_input_fn` method to create an input
function from pandas dataframes.
Each continuous column in the train or test dataframe
will be converted into a `Tensor`, which in general is a good format to
represent dense data. For categorical data, we must represent the data as a
`SparseTensor`. This data format is good for representing sparse data.
Another more advanced way to represent input data would be to
construct an [Inputs And Readers](../api_guides/python/io_ops.md#inputs-and-readers)
that represents a file or other data source, and iterates through the file as
TensorFlow runs the graph.

```python
def input_fn(data_file, num_epochs, shuffle):
  """Input builder function."""
  df_data = pd.read_csv(
      tf.gfile.Open(data_file),
      names=CSV_COLUMNS,
      skipinitialspace=True,
      engine="python",
      skiprows=1)
  # remove NaN elements
  df_data = df_data.dropna(how="any", axis=0)
  labels = df_data["income_bracket"].apply(lambda x: ">50K" in x).astype(int)
  return tf.estimator.inputs.pandas_input_fn(
      x=df_data,
      y=labels,
      batch_size=100,
      num_epochs=num_epochs,
      shuffle=shuffle,
      num_threads=5)
```

## Selecting and Engineering Features for the Model

Selecting and crafting the right set of feature columns is key to learning an
effective model. A **feature column** can be either one of the raw columns in
the original dataframe (let's call them **base feature columns**), or any new
columns created based on some transformations defined over one or multiple base
columns (let's call them **derived feature columns**). Basically, "feature
column" is an abstract concept of any raw or derived variable that can be used
to predict the target label.

### Base Categorical Feature Columns

To define a feature column for a categorical feature, we can create a
`CategoricalColumn` using the tf.feature_column API. If you know the set of all
possible feature values of a column and there are only a few of them, you can
use `categorical_column_with_vocabulary_list`. Each key in the list will get
assigned an auto-incremental ID starting from 0. For example, for the `gender`
column we can assign the feature string "Female" to an integer ID of 0 and
"Male" to 1 by doing:

```python
gender = tf.feature_column.categorical_column_with_vocabulary_list(
    "gender", ["Female", "Male"])
```

What if we don't know the set of possible values in advance? Not a problem. We
can use `categorical_column_with_hash_bucket` instead:

```python
occupation = tf.feature_column.categorical_column_with_hash_bucket(
    "occupation", hash_bucket_size=1000)
```

What will happen is that each possible value in the feature column `occupation`
will be hashed to an integer ID as we encounter them in training. See an example
illustration below:

ID  | Feature
--- | -------------
... |
9   | `"Machine-op-inspct"`
... |
103 | `"Farming-fishing"`
... |
375 | `"Protective-serv"`
... |

No matter which way we choose to define a `SparseColumn`, each feature string
will be mapped into an integer ID by looking up a fixed mapping or by hashing.
Note that hashing collisions are possible, but may not significantly impact the
model quality. Under the hood, the `LinearModel` class is responsible for
managing the mapping and creating `tf.Variable` to store the model parameters
(also known as model weights) for each feature ID. The model parameters will be
learned through the model training process we'll go through later.

We'll do the similar trick to define the other categorical features:

```python
education = tf.feature_column.categorical_column_with_vocabulary_list(
    "education", [
        "Bachelors", "HS-grad", "11th", "Masters", "9th",
        "Some-college", "Assoc-acdm", "Assoc-voc", "7th-8th",
        "Doctorate", "Prof-school", "5th-6th", "10th", "1st-4th",
        "Preschool", "12th"
    ])
marital_status = tf.feature_column.categorical_column_with_vocabulary_list(
    "marital_status", [
        "Married-civ-spouse", "Divorced", "Married-spouse-absent",
        "Never-married", "Separated", "Married-AF-spouse", "Widowed"
    ])
relationship = tf.feature_column.categorical_column_with_vocabulary_list(
    "relationship", [
        "Husband", "Not-in-family", "Wife", "Own-child", "Unmarried",
        "Other-relative"
    ])
workclass = tf.feature_column.categorical_column_with_vocabulary_list(
    "workclass", [
        "Self-emp-not-inc", "Private", "State-gov", "Federal-gov",
        "Local-gov", "?", "Self-emp-inc", "Without-pay", "Never-worked"
    ])
native_country = tf.feature_column.categorical_column_with_hash_bucket(
    "native_country", hash_bucket_size=1000)
```

### Base Continuous Feature Columns

Similarly, we can define a `NumericColumn` for each continuous feature column
that we want to use in the model:

```python
age = tf.feature_column.numeric_column("age")
education_num = tf.feature_column.numeric_column("education_num")
capital_gain = tf.feature_column.numeric_column("capital_gain")
capital_loss = tf.feature_column.numeric_column("capital_loss")
hours_per_week = tf.feature_column.numeric_column("hours_per_week")
```

### Making Continuous Features Categorical through Bucketization

Sometimes the relationship between a continuous feature and the label is not
linear. As an hypothetical example, a person's income may grow with age in the
early stage of one's career, then the growth may slow at some point, and finally
the income decreases after retirement. In this scenario, using the raw `age` as
a real-valued feature column might not be a good choice because the model can
only learn one of the three cases:

1.  Income always increases at some rate as age grows (positive correlation),
1.  Income always decreases at some rate as age grows (negative correlation), or
1.  Income stays the same no matter at what age (no correlation)

If we want to learn the fine-grained correlation between income and each age
group separately, we can leverage **bucketization**. Bucketization is a process
of dividing the entire range of a continuous feature into a set of consecutive
bins/buckets, and then converting the original numerical feature into a bucket
ID (as a categorical feature) depending on which bucket that value falls into.
So, we can define a `bucketized_column` over `age` as:

```python
age_buckets = tf.feature_column.bucketized_column(
    age, boundaries=[18, 25, 30, 35, 40, 45, 50, 55, 60, 65])
```

where the `boundaries` is a list of bucket boundaries. In this case, there are
10 boundaries, resulting in 11 age group buckets (from age 17 and below, 18-24,
25-29, ..., to 65 and over).

### Intersecting Multiple Columns with CrossedColumn

Using each base feature column separately may not be enough to explain the data.
For example, the correlation between education and the label (earning > 50,000
dollars) may be different for different occupations. Therefore, if we only learn
a single model weight for `education="Bachelors"` and `education="Masters"`, we
won't be able to capture every single education-occupation combination (e.g.
distinguishing between `education="Bachelors" AND occupation="Exec-managerial"`
and `education="Bachelors" AND occupation="Craft-repair"`). To learn the
differences between different feature combinations, we can add **crossed feature
columns** to the model.

```python
education_x_occupation = tf.feature_column.crossed_column(
    ["education", "occupation"], hash_bucket_size=1000)
```

We can also create a `CrossedColumn` over more than two columns. Each
constituent column can be either a base feature column that is categorical
(`SparseColumn`), a bucketized real-valued feature column (`BucketizedColumn`),
or even another `CrossColumn`. Here's an example:

```python
age_buckets_x_education_x_occupation = tf.feature_column.crossed_column(
    [age_buckets, "education", "occupation"], hash_bucket_size=1000)
```

## Defining The Logistic Regression Model

After processing the input data and defining all the feature columns, we're now
ready to put them all together and build a Logistic Regression model. In the
previous section we've seen several types of base and derived feature columns,
including:

*   `CategoricalColumn`
*   `NumericColumn`
*   `BucketizedColumn`
*   `CrossedColumn`

All of these are subclasses of the abstract `FeatureColumn` class, and can be
added to the `feature_columns` field of a model:

```python
base_columns = [
    gender, native_country, education, occupation, workclass, relationship,
    age_buckets,
]
crossed_columns = [
    tf.feature_column.crossed_column(
        ["education", "occupation"], hash_bucket_size=1000),
    tf.feature_column.crossed_column(
        [age_buckets, "education", "occupation"], hash_bucket_size=1000),
    tf.feature_column.crossed_column(
        ["native_country", "occupation"], hash_bucket_size=1000)
]

model_dir = tempfile.mkdtemp()
m = tf.estimator.LinearClassifier(
    model_dir=model_dir, feature_columns=base_columns + crossed_columns)
```

The model also automatically learns a bias term, which controls the prediction
one would make without observing any features (see the section "How Logistic
Regression Works" for more explanations). The learned model files will be stored
in `model_dir`.

## Training and Evaluating Our Model

After adding all the features to the model, now let's look at how to actually
train the model. Training a model is just a one-liner using the tf.estimator
API:

```python
# set num_epochs to None to get infinite stream of data.
m.train(
    input_fn=input_fn(train_file_name, num_epochs=None, shuffle=True),
    steps=train_steps)
```

After the model is trained, we can evaluate how good our model is at predicting
the labels of the holdout data:

```python
results = m.evaluate(
    input_fn=input_fn(test_file_name, num_epochs=1, shuffle=False),
    steps=None)
print("model directory = %s" % model_dir)
for key in sorted(results):
  print("%s: %s" % (key, results[key]))
```

The first line of the output should be something like `accuracy: 0.83557522`,
which means the accuracy is 83.6%. Feel free to try more features and
transformations and see if you can do even better!

If you'd like to see a working end-to-end example, you can download our
[example code](https://www.tensorflow.org/code/tensorflow/examples/learn/wide_n_deep_tutorial.py).
and set the `model_type` flag to `wide`.

## Adding Regularization to Prevent Overfitting

Regularization is a technique used to avoid **overfitting**. Overfitting happens
when your model does well on the data it is trained on, but worse on test data
that the model has not seen before, such as live traffic. Overfitting generally
occurs when a model is excessively complex, such as having too many parameters
relative to the number of observed training data. Regularization allows for you
to control your model's complexity and makes the model more generalizable to
unseen data.

In the Linear Model library, you can add L1 and L2 regularizations to the model
as:

```
m = tf.estimator.LinearClassifier(
    model_dir=model_dir, feature_columns=base_columns + crossed_columns,
    optimizer=tf.train.FtrlOptimizer(
      learning_rate=0.1,
      l1_regularization_strength=1.0,
      l2_regularization_strength=1.0),
    model_dir=model_dir)
```

One important difference between L1 and L2 regularization is that L1
regularization tends to make model weights stay at zero, creating sparser
models, whereas L2 regularization also tries to make the model weights closer to
zero but not necessarily zero. Therefore, if you increase the strength of L1
regularization, you will have a smaller model size because many of the model
weights will be zero. This is often desirable when the feature space is very
large but sparse, and when there are resource constraints that prevent you from
serving a model that is too large.

In practice, you should try various combinations of L1, L2 regularization
strengths and find the best parameters that best control overfitting and give
you a desirable model size.

## How Logistic Regression Works

Finally, let's take a minute to talk about what the Logistic Regression model
actually looks like in case you're not already familiar with it. We'll denote
the label as \\(Y\\), and the set of observed features as a feature vector
\\(\mathbf{x}=[x_1, x_2, ..., x_d]\\). We define \\(Y=1\\) if an individual earned >
50,000 dollars and \\(Y=0\\) otherwise. In Logistic Regression, the probability of
the label being positive (\\(Y=1\\)) given the features \\(\mathbf{x}\\) is given
as:

$$ P(Y=1|\mathbf{x}) = \frac{1}{1+\exp(-(\mathbf{w}^T\mathbf{x}+b))}$$

where \\(\mathbf{w}=[w_1, w_2, ..., w_d]\\) are the model weights for the features
\\(\mathbf{x}=[x_1, x_2, ..., x_d]\\). \\(b\\) is a constant that is often called
the **bias** of the model. The equation consists of two parts—A linear model and
a logistic function:

*   **Linear Model**: First, we can see that \\(\mathbf{w}^T\mathbf{x}+b = b +
    w_1x_1 + ... +w_dx_d\\) is a linear model where the output is a linear
    function of the input features \\(\mathbf{x}\\). The bias \\(b\\) is the
    prediction one would make without observing any features. The model weight
    \\(w_i\\) reflects how the feature \\(x_i\\) is correlated with the positive
    label. If \\(x_i\\) is positively correlated with the positive label, the
    weight \\(w_i\\) increases, and the probability \\(P(Y=1|\mathbf{x})\\) will be
    closer to 1. On the other hand, if \\(x_i\\) is negatively correlated with the
    positive label, then the weight \\(w_i\\) decreases and the probability
    \\(P(Y=1|\mathbf{x})\\) will be closer to 0.

*   **Logistic Function**: Second, we can see that there's a logistic function
    (also known as the sigmoid function) \\(S(t) = 1/(1+\exp(-t))\\) being applied
    to the linear model. The logistic function is used to convert the output of
    the linear model \\(\mathbf{w}^T\mathbf{x}+b\\) from any real number into the
    range of \\([0, 1]\\), which can be interpreted as a probability.

Model training is an optimization problem: The goal is to find a set of model
weights (i.e. model parameters) to minimize a **loss function** defined over the
training data, such as logistic loss for Logistic Regression models. The loss
function measures the discrepancy between the ground-truth label and the model's
prediction. If the prediction is very close to the ground-truth label, the loss
value will be low; if the prediction is very far from the label, then the loss
value would be high.

## Learn Deeper

If you're interested in learning more, check out our
[Wide & Deep Learning Tutorial](../tutorials/wide_and_deep.md) where we'll show you how to
combine the strengths of linear models and deep neural networks by jointly
training them using the tf.estimator API.
