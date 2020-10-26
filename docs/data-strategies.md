# Data Strategies

*Data Strategy is the source of data, i.e., population. It knows the underlying model, and its properties*. During [research preperation](flow.md#prepare-research), Researcher reaches to Data Strategy object and populates — ie., generates/collects data for — its Experiment.

Parameters of Data Strategy are intertwined with Experiment's parameters. Before defining the the model, we need to specify the structure of our design, number of observations in each group, and the [number of replications](/decision-strategies.md#post-qrp-decision-and-replication-stage).


```json
{
    "experiment_parameters": {
        "n_reps": 5,
        "n_conditions": 2,
        "n_dep_vars": 1,
        "n_obs": 25,
        "data_strategy": {
            "name": "",
            ...
        }
    }
}
```

The structure of our design is detemrined by the number of treatment conditions, *n* (`n_conditions`) and the number of dependent variables in each condition, *d* (`n_dep_vars`). After specifying our design, each group is being populated by `n_obs` observations based on the given model, specified in `data_strategy`. We can select the type of model by setting `name` variables of the `data_strategy` parameter in the config file. Two available options are [Linear Model](/data-strategies.md#linear-model) and [Graded Response Model](/data-strategies.md#graded-response-model). Based on your model of choice, you must provide different set of variables.

![Figure 1. Experiment Design](/figures/experiment-design.png)


<!--
 | **Parameters** | **Value** / **Type** |
|:---------------|:---------------------|
| `n_conditions` | n<sub>c</sub>, `int` |
| `n_dep_vars`   | n<sub>d</sub>, `int` |
| `n_obs`        | n<sub>o</sub>, `int` |
| `n_reps`       | n<sub>r</sub>, `int` |
-->

<!-- Since Data Strategy is aware of all the underlying models, parameters and distributions, it is capale of providing data at any points during the simulation.  -->

<!-- As mentioned, methods like [optional stopping](/hacking-strategies.md#hacking-strategies-optional-stopping) needs to add new data points to the already existing measurements. Requiring data strategies to produce *new* data points helps with implementation of such hacking strategies. -->

## Linear Model

In the case of Linear Model, SAM uses multi-variate normal distribution
with the mean of $\mu$ and covariance matrix of $\Sigma$,
$X \sim MN(\mu, \Sigma)$.

You can change the parameters accordingly to implement your own design.
For example, in order to set up an experiment with no covariance, you
may set the `covs` to `0`. This will prompt SAM to only use the diagonal
row of the covariance matrix.

| **Parameters** | **Value** / **Type**                 |
|:---------------|:-------------------------------------|
| `means`        | *μ*, `double` or `array`             |
| `stddevs`      | *σ<sup>2</sup>*, `double` or `array` |
| `covs`         | *Σ*, `double`, `matrix`              |

!!! datastartegy "Linear Model Configuration: Multivariate Normal"
    ```json
    {
    "n_conditions": 2,
    "n_dep_vars": 1,
    "n_obs": 25,
    "data_strategy": {
        "name": "LinearModel",
        "measurements": {
            "means": [0, 0.2],
            "covs": 0.0,
            "stddevs": 1.0,
        },
        "errors": {
            "means": [0, 0],
            "covs": 0.0,
            "stddevs": 1.0,
        }
    }
    ```


!!! datastartegy "Linear Model Configuration: Custom Distributions"
    ```json
    {
    "data_strategy": {
        "n_conditions": 2,
        "n_dep_vars": 1,
        "n_obs": 25,
        "name": "LinearModel",
        "measurements": [
            {
                "dist": "normal_distribution",
                "mean": 0,
                "stddev": 1
            },
            {
                "dist": "normal_distribution",
                "mean": 0,
                "stddev": 1
            }
        ],
        "errors": [
            {
                "dist": "cauchy_distribution",
                "a": 0,
                "b": 0.1
            },
            {
                "dist": "cauchy_distribution",
                "a": 0,
                "b": 0.1
            }
        ]
    }
    ```

!!! warning
    Length of all parameters should complies with the given size of the
    study. For instance, if you are planning to run a study with 2 dependent
    variables and 2 conditions, you need to specify an array of 4 for the
    mean of each group.


## Graded Response Model

The current implementation of the Graded Response Model is based on the
generalization of Rasch Model. The probablity of person $j$ answering an
item $i$ correctly, $Pr(X_{ij} = 1)$, can be calculated based on the
difficulty $\beta$ of the item $i$ and the ability $\theta$ of a person
$j$ with the following model \[from Marjan\]:

$$ Pr(X_{ij} = 1) = \frac{exp(\theta_j - \beta_i)}{1 + exp(\theta_j - \beta_i)} $$

| **Parameters** | **Value** / **Type**     |
|:---------------|:-------------------------|
| `n_categories` | `int`                    |
| `n_items`      | `int`                    |
| `abilities`    | *θ*, `double` or `array` |
| `difficulties` | *β*, `double` or `array` |

After calculating all responses of person $j$ to all items, the sum
score of all answers is calcuated for each person by adding all the item
scores \[from, Marjan 2014\].

!!! datastrategy "Graded Response Model Configuration"

    ```json
    {
        "name": "GradedResponseModel"
        "data_strategy": {
            "n_categories": 4,
            "n_items": 3,
            "abilities": [0, 0.2],
            "difficulties": 0,
        }
    }
    ```
