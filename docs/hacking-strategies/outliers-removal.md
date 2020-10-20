# Outliers Removal

Removing outliers is another popular researcher's degrees of freedom. While use of outliers removal is not prohibited, most researcher are not aware of its consequences.

Outliers removal method can be implemented in several different ways as well. In the simplest case, a researcher will decide to remove a data point from a dataset if the value is further than a distance from the sample mean. One common method is to compare the distance of a value to different multiplier of standard deviation. This type of outliers removal can be deployed by defining the following parameters.


![Outliers Removal Algorithm](/hacking-strategies/figures/outlier-removal.png)


!!! hackingstrategy “Outlier Removal”
		```json
		{
		  "name": "Outlier Removal",
		  "num": 2,
		  "n_attempts": 3,
		  "max_attempts": 10,
		  "min_observations": 20,
		  "multipliers": [3, 2, 1]
		}
		```

The main body of outliers removal algorithm is implemented similarly to the optional stopping. The researcher remove add $n$ items in `n_attempts` before stopping the process, or achieving significant results. You can also specify a list of `multipliers`. The algorithm performs *t* attempts to remove *n* outliers from a dataset based on given multipliers, $\sigma_i$. The algorithm will advance if there is no item left to be removed at $i < n$ attempts, or after *n* attempts.



-  `num`, *n*, `int`, indicates number of items to be moved at each attempt
- `n_attempts`, indicates number of attempts to move outliers for ch multiplier
- `max_attempts`, indicates the maximum number of erations before opping the process
- `min_observations`, indicates the minimum number of servations. Outliers moval stops removing lues when a group aches in\_observation\`.
- `multipliers`, indicates a list of multipliers be used
- `order`, indicates the order in which observations will be removed from Experiment

You can achieve different variants of outliers removal method by modifying its parameters. For instance, setting `num = 1` and choosing large values for `n_attempts` will remove the outliers one-by-one from `Experiment`. You can control this process by specifying a list of `multipliers`.
