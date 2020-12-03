# Optional Stopping

Optional stopping — in its most prominent form — is the practice of adding new observations to an Experiment after the initial data collection is concluded. Often the main incentive behind applying this method is to push one of the dependent variable to significant. Like [selective reporting](selective-reporting.md), optional stopping sits high up in the list of defensible and prevalent questionable research practices [cite, cite].

> maybe I can add more “fact” about each method

![Optional Stopping Algorithm](/hacking-strategies/figures/optional-stopping.png)

Optional stopping can be performed in various ways. SAM’s implementation tries to provide a wide range of customizations in order to be able to cover different forms of optional stopping. Figure 1 shows the main body of the optional stopping algorithm as implemented in SAM. Like most hacking strategies, the optional stopping algorithm is implemented based on the fact that often a researcher perform multiple attempts to achieve significance, `n_attempts`.

At each attempt, researcher reaches to [data strategy](/data-strategies.md) and request `num` new observations for each group. Data strategy returns exactly `num` new observations from the same distribution that been used to initialize the Experiment. For instance, if we have configured a [graded response model](/data-strategies.md#graded-response-model) as our population, each newly generated observation will be calculated exactly based on the given model, e.g., Rasch Model.

After adding new observations, all statistics, tests, and effects will be recalled and the Researcher continue to evaluate the `stopping_condition`, if there is any. If stopping condition is satisfied, the Researcher quits the algorithm, and moves to the defined **selection → decision** sequence. 

The configuration below showcases a sample implementation of optional stopping as it has been used in [Maassen](/examples/esther_first_year.md) simulation.

!!! hackingstrategy "Optional Stopping"
    ```json
    {
      "name": "OptionalStopping",
      "target": "Both",
      "prevalence": 1,
      "defensibility": 1,
      "max_attempts": 1,
      "n_attempts": 1,
      "num": 0,
      "ratio": 0.3
    }
    ```

Besides [common parameters](/hacking-strategies.md#hacking-strategy-specification) shared between all hacking strategies, optional stopping specific parameters are as follow:

- `num`, indicates number of observations be added on each attempt.
- `ratio`, indicates a multiplier that its going to be used to calculate the number of new observations — based on current *N* — to be added to each group.
- `n_attempts`, indicates number of attempts fore stopping the process.
