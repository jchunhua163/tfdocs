<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.RunConfig" />
<meta itemprop="property" content="cluster_spec"/>
<meta itemprop="property" content="evaluation_master"/>
<meta itemprop="property" content="is_chief"/>
<meta itemprop="property" content="keep_checkpoint_every_n_hours"/>
<meta itemprop="property" content="keep_checkpoint_max"/>
<meta itemprop="property" content="log_step_count_steps"/>
<meta itemprop="property" content="master"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="num_ps_replicas"/>
<meta itemprop="property" content="num_worker_replicas"/>
<meta itemprop="property" content="save_checkpoints_secs"/>
<meta itemprop="property" content="save_checkpoints_steps"/>
<meta itemprop="property" content="save_summary_steps"/>
<meta itemprop="property" content="session_config"/>
<meta itemprop="property" content="task_id"/>
<meta itemprop="property" content="task_type"/>
<meta itemprop="property" content="tf_random_seed"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="replace"/>
</div>

# tf.estimator.RunConfig

## Class `RunConfig`





Defined in [`tensorflow/python/estimator/run_config.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/run_config.py).

This class specifies the configurations for an `Estimator` run.

## Properties

<h3 id="cluster_spec"><code>cluster_spec</code></h3>



<h3 id="evaluation_master"><code>evaluation_master</code></h3>



<h3 id="is_chief"><code>is_chief</code></h3>



<h3 id="keep_checkpoint_every_n_hours"><code>keep_checkpoint_every_n_hours</code></h3>



<h3 id="keep_checkpoint_max"><code>keep_checkpoint_max</code></h3>



<h3 id="log_step_count_steps"><code>log_step_count_steps</code></h3>



<h3 id="master"><code>master</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>



<h3 id="num_ps_replicas"><code>num_ps_replicas</code></h3>



<h3 id="num_worker_replicas"><code>num_worker_replicas</code></h3>



<h3 id="save_checkpoints_secs"><code>save_checkpoints_secs</code></h3>



<h3 id="save_checkpoints_steps"><code>save_checkpoints_steps</code></h3>



<h3 id="save_summary_steps"><code>save_summary_steps</code></h3>



<h3 id="session_config"><code>session_config</code></h3>



<h3 id="task_id"><code>task_id</code></h3>



<h3 id="task_type"><code>task_type</code></h3>



<h3 id="tf_random_seed"><code>tf_random_seed</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__()
```



<h3 id="replace"><code>replace</code></h3>

``` python
replace(**kwargs)
```

Returns a new instance of `RunConfig` replacing specified properties.

Only the properties in the following list are allowed to be replaced:
  - `model_dir`.
  - `tf_random_seed`,
  - `save_summary_steps`,
  - `save_checkpoints_steps`,
  - `save_checkpoints_secs`,
  - `session_config`,
  - `keep_checkpoint_max`,
  - `keep_checkpoint_every_n_hours`,
  - `log_step_count_steps`,

In addition, either `save_checkpoints_steps` or `save_checkpoints_secs`
can be set (should not be both).

#### Args:

  **kwargs: keyword named properties with new values.


#### Raises:

* <b>`ValueError`</b>: If any property name in `kwargs` does not exist or is not
    allowed to be replaced, or both `save_checkpoints_steps` and
    `save_checkpoints_secs` are set.


#### Returns:

  a new instance of `RunConfig`.



